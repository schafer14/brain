1. Write a non concurrent function first (separate the what from the how)
2. Use higher levels of abstraction/library
	1. Conc
	2. errgroup
	3. proto actor
3. Use Go 1.22
4. Use the `--race` flag 
5. Test and Benchmark (avoid premature optimisation)
6. Make the concurrency transparent to client
7. Wrap peripheral concerns using middleware
8. Use bounded concurrency 
Two bonus recommendations
1. Understand work stealing algorithm
2. Hide implementation details in packages
3. Use a good type signature
	1. [func (p *ResultContextPool[T]) Go(f func(context.Context) (T, error))](https://pkg.go.dev/github.com/sourcegraph/conc/pool#ResultContextPool.Go)

## Use higher level concurrent abstractions
- Go sync packages was created before context.Context was added to the language in 1.7
- https://go.dev/doc/go1.7
- 