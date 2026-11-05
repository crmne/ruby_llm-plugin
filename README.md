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
