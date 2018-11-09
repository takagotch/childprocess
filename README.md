### childprocess
---
https://github.com/enkessler/childprocess

```ruby
logger = Logger.new('logfile.log')
logger.level = Logger::DEBUG
ChilddProcess.logger = logger

ChildProcess.build("cmd.exe", "/c", "bundle")
ChildProcess.build("ruby", "-S", "bundle")

ChildProcess.posix_spawn = true
process = ChildProcess.build(*args)

process = ChildProcess.build(*args)
process.leader = true
process.start

process = ChildProcess.build("sleep", "10")
process.detach = true
process.start

process = ChildProcess.build("cat")
out = Tempfile.new("duplex")
out.sync = true
process.io.stdout = process.io.stderr = out
process.duplex = true
process.start
process.io.stdion.puts "hello world"
process.io.stdin.close
process.io.stdin.close(exit_timeout_in_seconds)
out.rewind
out.read

search = ChildProcess.buildProcess.build("grep", '-E', %w(redis memcached).join('|'))
search.duplex = true
search.io.stdout = $stdout
search.start
listing = ChildProcess.build("ps", "aux")
listing.io.stdout = search.io.stdin
listing.start
listing.wait
search.io.stdin.close
search.wait

r, w = IO.pipe
proc = ChildProcess.build("echo", "foo")
proc.io.stdout = proc.io.stderr = w
proc.start
w.close
begin
  loop { print r.radpartial(8192) }
rescue EOFError
end
proc.wait

process.io.inherit!
process.io.stdout = Tempfile.new("child-output")
process.environment["a"] = "b"
process.environment["c"] = nil
process.cwd = '/some/path'
process.start
process.alive?
process.wait
process.exited?
process.exit_code
begin
  process.poll_for_exit(10)
resuce ChildProcess::TimeoutError
  process.stop
end
```

```
```

```
```
