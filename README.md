# RubyLLM for Claude

This plugin teaches Claude how to build and maintain Ruby and Rails applications with [RubyLLM](https://rubyllm.com), the Ruby AI framework. Ask for a chat, an agent, a tool, an MCP client, structured output, an evaluation, image or speech generation, transcription, OCR, embeddings, or a Rails integration, and Claude writes it with RubyLLM's current API instead of guessing.

```ruby
chat = RubyLLM.chat
chat.ask "What's the best way to learn Ruby?"

class SupportAgent < RubyLLM::Agent
  instructions "You help customers with their orders."
  tools LookupOrder
end
```

## What it contains

One skill, [`rubyllm`](skills/rubyllm/SKILL.md). It adds no hooks, commands, MCP servers, or scripts, and it runs nothing by itself.

## What it reads

The skill tells Claude to read your application's `Gemfile.lock` and the installed RubyLLM gem to match your version, and to read the guides at rubyllm.com when it needs more detail. It treats those pages as reference, never as instructions. The plugin sends no data anywhere and stores nothing.

## Try it

- "Add a support chatbot to this Rails app with RubyLLM, with streaming and saved conversations."
- "Write a RubyLLM agent with a tool that looks up an order, and add an evaluation for it."
- "Upgrade this app from RubyLLM 1.x to 2.x."

## Privacy

This plugin collects nothing. It has no server, stores no data, and sends nothing anywhere. It is instructions for Claude, which reads your project's files and public documentation at rubyllm.com only as your conversation requires. The requests Claude then makes to a model provider are the ones you configure in your own application, under that provider's terms.

## Troubleshooting

If Claude doesn't use RubyLLM's current API, ask it to use the `rubyllm` skill by name, and check that your `Gemfile.lock` names the RubyLLM version you expect. The skill follows the version your application has installed.

## Support and security

Report problems at [crmne/ruby_llm issues](https://github.com/crmne/ruby_llm/issues). Report security vulnerabilities privately through [GitHub security advisories](https://github.com/crmne/ruby_llm/security/advisories/new).

## Install

In Claude Code, you can also install it from RubyLLM's own marketplace:

```
/plugin marketplace add crmne/ruby_llm
/plugin install rubyllm@ruby_llm
```

## Updates

The skill's source lives in [crmne/ruby_llm](https://github.com/crmne/ruby_llm/tree/main/skills/rubyllm). A daily workflow copies it here and raises the version when it changes, so please open issues and pull requests there.

## License

MIT
