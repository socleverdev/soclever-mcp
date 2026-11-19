# soclever connector

Connect your AI assistant to [soclever](https://soclever.io) and turn your own material into a private course.

This repository holds setup instructions and a small Claude Code plugin. It is **not** an open-source server: the connection itself is a hosted soclever service, and the app behind it is private. The plugin only tells Claude Code where the connection is. You sign in with your soclever account; there is no key to copy.

Any soclever account can connect. Questions go to the [soclever support page](https://soclever.io/support).

## Other assistants

For every other assistant, follow the [soclever setup page](https://soclever.io/connect). It is the one place we keep current instructions, so they aren't repeated here.

## Install in Claude Code

1. Add the soclever plugin catalog (once per computer). In Claude Code, run:

   ```text
   /plugin marketplace add socleverdev/soclever-mcp
   ```

2. Install the plugin:

   ```text
   /plugin install soclever-mcp@soclever
   ```

   Choose **Install for you** so it works in every project. Run `/reload-plugins` if Claude Code asks you to.

3. Sign in. Run `/mcp`, choose **soclever**, and sign in. Your browser opens soclever's approval screen, which lists what Claude Code will be able to do. Approve it, then return to Claude Code.

## Check the connection

Ask Claude Code:

```text
Check my soclever connection.
```

It uses the connection's read-only check, which changes nothing. The answer says whether you're connected, how many new courses you've started through an assistant today and the daily limit, and what this connection is allowed to do.

Then try a first course:

```text
Make a private soclever course from the files in this folder.
```

Claude Code may ask you to allow soclever's tools and the commands that upload your files. Those requests are expected.

## Good to know

- **Original files or text only.** A course is complete when your original files are uploaded. If an upload fails and only the text is sent, the course is made from that text alone: layout, pictures, scanned pages and recording detail are left out.
- **Daily limit.** New courses started through an assistant count toward a daily limit, and what you can make follows your soclever plan. The connection check shows how many you have left today.
- **What soclever sees.** soclever never connects to your email or Slack. It only receives what your assistant sends to make a course.

## Disconnect

1. In soclever, open **Settings → Assistant access**, select the assistant, and choose **Remove**.
2. In Claude Code, run `/mcp`, choose **soclever**, and choose **Clear authentication**. Or uninstall the plugin (below).

## Update

Run this in your terminal:

```bash
claude plugin update soclever-mcp@soclever
```

Or, in Claude Code, run `/plugin`, open the **Installed** tab, select **soclever-mcp**, and choose **Update now**.

## Uninstall

1. Run this in your terminal:

   ```bash
   claude plugin uninstall soclever-mcp@soclever
   ```

2. Optional: remove the plugin catalog too.

   ```bash
   claude plugin marketplace remove soclever
   ```

3. Remove the assistant in soclever **Settings → Assistant access**, so its sign-in can't be used again.

## License

The files in this repository are available under the [MIT License](LICENSE). In that license, "the Software" means only the documentation and configuration files in this repository. It does not cover, and grants no rights to, the hosted soclever service, the soclever app or its source code, the soclever name, logo or other brand assets, or any content made with or stored in soclever. Using the service is subject to soclever's own terms.
