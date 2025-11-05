nix run .#claude-code -- --version

/Users/noah/.cargo/bin/httpjail --help

Basic blocking (exact domain match):
  httpjail --js "r.host !== 'claude.ai'" -- nix run .#claude-code

  Advanced blocking (includes all subdomains):
  httpjail --js "!r.host.endsWith('claude.ai')" -- nix run .#claude-code

  With request logging:
  httpjail --request-log blocked-requests.log --js "r.host !== 'claude.ai'" -- nix run .#claude-code