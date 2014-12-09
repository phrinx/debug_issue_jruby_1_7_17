Minimal project to reproduce NPE thrown with the newly released jruby 1.7.17

To reproduce, run:

     $ bundle install && rspec test.rb --debug
     
     Example: |jruby-1.7.17@debug_issue| thq-m-dkoeh01 in ~/workspace/debug_issue_with_jruby_1_7_17
     ±  |master ✓| → rspec test.rb --debug
     /Users/dkoehler/.rvm/gems/jruby-1.7.17@debug_issue/gems/simplecov-0.9.1/lib/simplecov.rb:31 warning: tracing (e.g. set_trace_func) will not capture all events without --debug flag
     /Users/dkoehler/.rvm/gems/jruby-1.7.17@debug_issue/gems/ruby-debug-base-0.10.4-java/lib/ruby-debug-base.rb:214 warning: tracing (e.g. set_trace_func) will not capture all events without --debug flag
     Ruby.java:3065:in `callEventHooks': java.lang.NullPointerException
     	from ASTInterpreter.java:239:in `callTraceFunction'
     	from NewlineNode.java:101:in `interpret'
     	from EnsureNode.java:98:in `interpret'
     	from ASTInterpreter.java:74:in `INTERPRET_METHOD'
     	from InterpretedMethod.java:268:in `call'
     	from DefaultMethod.java:235:in `call'
     	from CachingCallSite.java:366:in `cacheAndCall'
     	from CachingCallSite.java:238:in `call'
     	from FCallThreeArgNode.java:40:in `interpret'
     	from CallNoArgNode.java:60:in `interpret'
     	from DAsgnNode.java:110:in `interpret'
     	from NewlineNode.java:105:in `interpret'
     	from BlockNode.java:71:in `interpret'
     	from ASTInterpreter.java:112:in `INTERPRET_BLOCK'
     	from Interpreted19Block.java:206:in `evalBlockBody'
     	from Interpreted19Block.java:194:in `yield'
     	from Interpreted19Block.java:125:in `call'
     	from Block.java:101:in `call'
     	from RubyProc.java:290:in `call'
     	from RubyProc.java:228:in `call'
     	from Ruby.java:3157:in `tearDown'
     	from Ruby.java:3141:in `tearDown'
     	from Main.java:294:in `internalRun'
     	from Main.java:217:in `run'
     	from Main.java:197:in `main'     
