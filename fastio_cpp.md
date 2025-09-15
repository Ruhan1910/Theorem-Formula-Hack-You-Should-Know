# ios::sync_with_stdio(false) 
1. By default, C++ iostream (cin, cout) are synchronized with C stdio (scanf, printf)
2. That means every operation tries to stay in lockstep with C I/O -> extra overhead.
3. Turning it off removes that overhead, making cin/cout faster
# cin.tie(nullptr): 
What tie() really do? Each stream (cin, cout, cerr, etc) can be tied to another stream. Being tied means that before any input operation on this stream, the tied stream gets flushed. What does that mean?
--When we print something like cout << "HELLO"; the text "HELLO" is not always sent to the terminal immediately; instead, it's stored in an output buffer (a chunk of memory). The buffer gets written out (flushed) 
to the terminal when 
1. The buffer is full or
2. You explicitly flush it, or
3. The program ends, or
4. A tie input (cin) forces it.

So flushing means take everything sitting in the buffer, and actually write it to the output(screen, file, etc)
You can flush manually with
1. cout << flush;
2. cout << endl;
3. cout.flush();

# Without flush
cout << "Enter n: "; // stays in buffer
cin >> n; // user sees nothing

with default tie (cin tied to cout): 
So every time you do (cin >> x;), it forces cout to flush first. This ensures that prompts like cout << "Enter n: "; will appear immediately before waiting for input.
1. Before cin >> n; runs, cout is flushed automatically, so "Enter n: " appears.
2. This is why cin is tied to cout by default - so prompts show up right away.

# If we use cin.tie(nullptr) // cin.tie(0) then:
It will untie cout from cin and
cout << "Enter n: "; //stay in buffer
cin >> n; //does not flush anymore

So the user might not see the "Enter n: " prompt until after typing something.

# Why disable automatic flush?
Because flushing is slow (it forces an immediate system call).
In competitive programming, you usually don't care about prompts, so you untie streams(cin.tie(0)) to avoid extra flushing and save time. 

# Note: 
Actually flushing = emptying the output buffer -> which means printing/sending the data right now.

# Why cout.tie(0) is not usefull?
1. Generally, cin is tied with cout. So cin.tie(0) unties cin from cout.
2. Cout is not tied to anything by default, so cout.tie(0) does nothing.

# use endl with fastio?
What does endl do?
1. prints a newline
2. flushes the buffer manually
So even if you have untied cin from cout, endl will still flush, because that is its job.
