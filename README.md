# Zendesk API MCP Server

    A comprehensive Model Context Protocol (MCP) server for interacting with the Zendesk API. This server provides tools and resources for managing Zendesk Support, Talk, Chat, and Guide products.

    ## Features

    - Complete coverage of Zendesk API functionality
    - Tools for managing tickets, users, organizations, and more
    - Resources for accessing Zendesk API documentation
    - Secure authentication with Zendesk API tokens

    ## Getting Started

    ### Prerequisites

    - Node.js 14 or higher
    - A Zendesk account with API access

    ### Installation

    1. Clone this repository
    2. Install dependencies:
       ```
       npm install
       ```
    3. Create a `.env` file with your Zendesk credentials:
       ```
       ZENDESK_SUBDOMAIN=your-subdomain
       ZENDESK_EMAIL=your-email@example.com
       ZENDESK_API_TOKEN=your-api-token
       ```

    ### Running the Server

    Start the server:
    ```
    npm start
    ```

    For development with auto-restart:
    ```
    npm run dev
    ```

    ### Testing with MCP Inspector

    Test the server using the MCP Inspector:
    ```
    npm run inspect
    ```

    ## Using with Claude Desktop

    1. Open your Claude Desktop config file:
       - **macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`
       - **Windows**: `%APPDATA%\Claude\claude_desktop_config.json`

    2. Add the Zendesk MCP server to the `mcpServers` section:
       ```json
       {
         "mcpServers": {
           "zendesk": {
             "command": "node",
             "args": ["/path/to/zendesk-mcp-server/src/index.js"],
             "env": {
               "ZENDESK_SUBDOMAIN": "your-subdomain",
               "ZENDESK_EMAIL": "your-email@example.com",
               "ZENDESK_API_TOKEN": "your-api-token"
             }
           }
         }
       }
       ```

    3. Replace `/path/to/zendesk-mcp-server` with the absolute path to where you cloned this repo.

    4. Restart Claude Desktop. You should see the Zendesk tools available in your conversation.

    ## Using with Claude Code

    Add the server to your Claude Code MCP settings (`~/.claude/settings.json`):

    ```json
    {
      "mcpServers": {
        "zendesk": {
          "command": "node",
          "args": ["/path/to/zendesk-mcp-server/src/index.js"],
          "env": {
            "ZENDESK_SUBDOMAIN": "your-subdomain",
            "ZENDESK_EMAIL": "your-email@example.com",
            "ZENDESK_API_TOKEN": "your-api-token"
          }
        }
      }
    }
    ```

    Alternatively, pass credentials via a `.env` file in the repo root instead of the `env` block — the server will load it automatically.

    ## Available Tools

    ### Tickets
    - `list_tickets`: List tickets in Zendesk
    - `get_ticket`: Get a specific ticket by ID
    - `get_ticket_comments`: Get all comments (and attachment metadata) for a ticket
    - `create_ticket`: Create a new ticket
    - `update_ticket`: Update an existing ticket
    - `delete_ticket`: Delete a ticket

    ### Users
    - `list_users`: List users in Zendesk
    - `get_user`: Get a specific user by ID
    - `create_user`: Create a new user
    - `update_user`: Update an existing user
    - `delete_user`: Delete a user

    ### Organizations
    - `list_organizations`: List organizations in Zendesk
    - `get_organization`: Get a specific organization by ID
    - `create_organization`: Create a new organization
    - `update_organization`: Update an existing organization
    - `delete_organization`: Delete an organization

    ### Groups
    - `list_groups`: List agent groups in Zendesk
    - `get_group`: Get a specific group by ID
    - `create_group`: Create a new agent group
    - `update_group`: Update an existing group
    - `delete_group`: Delete a group

    ### Macros
    - `list_macros`: List macros in Zendesk
    - `get_macro`: Get a specific macro by ID
    - `create_macro`: Create a new macro
    - `update_macro`: Update an existing macro
    - `delete_macro`: Delete a macro

    ### Views
    - `list_views`: List views in Zendesk
    - `get_view`: Get a specific view by ID
    - `create_view`: Create a new view
    - `update_view`: Update an existing view
    - `delete_view`: Delete a view

    ### Triggers
    - `list_triggers`: List triggers in Zendesk
    - `get_trigger`: Get a specific trigger by ID
    - `create_trigger`: Create a new trigger
    - `update_trigger`: Update an existing trigger
    - `delete_trigger`: Delete a trigger

    ### Automations
    - `list_automations`: List automations in Zendesk
    - `get_automation`: Get a specific automation by ID
    - `create_automation`: Create a new automation
    - `update_automation`: Update an existing automation
    - `delete_automation`: Delete an automation

    ### Search
    - `search`: Search across Zendesk data

    ### Help Center
    - `list_articles`: List Help Center articles
    - `get_article`: Get a specific Help Center article by ID
    - `create_article`: Create a new Help Center article
    - `update_article`: Update an existing Help Center article
    - `delete_article`: Delete a Help Center article

    ### Talk
    - `get_talk_stats`: Get Zendesk Talk statistics

    ### Chat
    - `list_chats`: List Zendesk Chat conversations

    ## Available Resources

    - `zendesk://docs/{section}`: Access documentation for different sections of the Zendesk API

    ## License

    MIT
