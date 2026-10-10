<p align="center"><img src="https://raw.githubusercontent.com/go-plot/brand/main/social/go-plot.png" alt="go-plot" width="720"></p>

# go-plot

🌐 **[Website](https://go-plot.github.io)** · 📚 **[Documentation](https://go-plot.github.io/docs/)**

**Pure-Go (CGO=0) plotting for go-ndarray: matplotlib-class figures to SVG and PNG, with real TeX in the labels.**

The object model and the defaults are matplotlib's — figure size, fonts, colour
cycle, margins, tick placement and tick labels — so a figure looks the way a
matplotlib user expects, and the parts that can be equal are **tested equal to
matplotlib**: tick locations and labels on 408 real axes, eight colormaps entry
for entry, and the layout of 30 figures. The API is the object-oriented one
most notebooks use (`fig, ax = plt.subplots(); ax.plot(...)`). What Go adds:
one static binary, `js/wasm`, no Python, and TeX labels set by a real TeX math
typesetter ([go-tex/math](https://github.com/go-tex/math)).

```go
fig, axs := plot.Subplots(1, 1)
ax := axs[0][0]
ax.Plot(x, y, plot.Label(`$\sin t$`))
ax.SetXLabel(`time $t$ (s)`)
ax.Legend()
fig.SavePNG(os.Stdout)
```

## Repositories

| Repo | What it is |
|------|------------|
| [**plot**](https://github.com/go-plot/plot) | the library: `Figure`, `Axes` and every plot type, ticks, colormaps, contours, the SVG and raster back-ends, TeX labels (Go 1.27.2 or later) |
| [**docs**](https://github.com/go-plot/docs) | the documentation site (Hugo + Hextra), served at [/docs/](https://go-plot.github.io/docs/) |
| [**go-plot.github.io**](https://github.com/go-plot/go-plot.github.io) | the landing page (Hugo) |
| [**brand**](https://github.com/go-plot/brand) | logo, icons and social images |

It is part of an ecosystem with [go-ndarray](https://github.com/go-ndarray/ndarray)
(NumPy-style arrays), [go-fft](https://github.com/go-fft/fft) (`numpy.fft`) and
[go-notebook](https://github.com/go-notebook/notebook) (Go notebooks), whose
kernel shows a figure through `Figure.Display`.
