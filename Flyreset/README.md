# FlyReset 2.0 — Fabric 26.3

Server-side mod; clients do not need it.

After a player joins, the mod waits 40 server ticks (about 2 seconds), then runs
`fly <playername> false` using the server command source. It does not change
`flying` or `mayfly` directly and does not register or replace `/fly`.
EssentialsCommand remains responsible for `/fly` and its permissions.

The GitHub workflow expects `.github/workflows/build.yml` at repository root
and the project inside `Flyreset/`. Upload the contents of this ZIP into the
root of your existing repository and commit. GitHub Actions publishes the
artifact `FlyReset-2.0-Fabric-26.3`.

Install by stopping the server, removing old `flyreset-1.0.0.jar`, placing
`flyreset-2.0.0.jar` in `mods`, keeping Fabric API installed, then restarting.

Check the server log for `Executed 'fly PLAYER false'` after a player joins.
