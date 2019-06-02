# KRATE.WUI

ASP.NET Core 2.1 Razor Pages web user interface self hosted by KRATE core service. Does not require IIS, NGINX, Apache or other webserver.

# Branches

Development - On going development of new features and components happens here. Do not build production binary from this branch.

TestNet - Considered feature complete. Tests and patches will be applied to ensure proper function of the new features. As well this branch will be for testing and patching any regressions, security flaws or stability issues. Do not build production binaries from this branch.

StageNet - Interally this code is considered production ready and is waiting for external audit. It is not expected that forking or breaking changes will be introduced into this branch before moving to MainNet but it is still not recommended to build production binaries from this branch.

MainNet - Production ready. Please build production binaries from this branch.