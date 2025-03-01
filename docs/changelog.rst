Changelog
=========
1.1.0
-----
Additions
~~~~~~~~~
- Added a widget to draw a histogram of features.

Changes
~~~~~~~
- The slice widget is now limited to slicing along the x/y dimensions. Support
  for slicing along z has been removed for now to make the code simpler.
- The slice widget now uses a slider to select the slice value.

Bug fixes
~~~~~~~~~
- Fixed creating 1D slices of 2D images.
- Removed the limitation that only the first 99 indices could be sliced using
  the slice widget.

1.0.2
-----
Bug fixes
~~~~~~~~~
- A full dataset is no longer read into memory when using ``HistogramWidget``.
  Only the current slice is loaded.
- Fixed compatibility with napari 0.4.18.

Changes
~~~~~~~
- Histogram bin limits are now caclualted from the slice being histogrammed, and
  not the whole dataset. This is as a result of the above bug fix.

1.0.1
-----
Bug fixes
~~~~~~~~~
- Pinned that maximum version of `napari` to 0.4.17, since ``napari-matplotlib``
  does not yet work with ``napari`` 0.4.18.

1.0.0
-----

New features
~~~~~~~~~~~~
- Added ``MPLWidget`` as a widget containing just a Matplotlib canvas
  without any association with a napari viewer.
- Added text to each widget indicating how many layers need to be selected
  for the widget to plot something.

Visual improvements
~~~~~~~~~~~~~~~~~~~
- The background of ``napari-matplotlib`` figures and axes is now transparent, and the text and axis colour respects the ``napari`` theme.
- The icons in the Matplotlib toolbar are now the same size as icons in the napari window.
- Custom style sheets can now be set to customise plots. See the user guide
  for more information.

Changes
~~~~~~~
- The scatter widgets no longer use a LogNorm() for 2D histogram scaling.
  This is to move the widget in line with the philosophy of using Matplotlib default
  settings throughout ``napari-matplotlib``. This still leaves open the option of
  adding the option to change the normalization in the future. If this is something
  you would be interested in please open an issue at https://github.com/matplotlib/napari-matplotlib.
- Labels plotting with the features scatter widget no longer have underscores
  replaced with spaces.
- ``NapariMPLWidget.update_layers()`` has been removed as it is intended to be
  private API. Use ``NapariMPLWidget.on_update_layers`` instead to implement
  funcitonality when layer selection is changed.
- The slice widget now only plots x-ticks at integer locations.

Bug fixes
~~~~~~~~~
- Importing ``napari-matplotlib`` no longer affects how plots are rendered in
  Jupyter notebooks.

Other
~~~~~
- ``napari-matplotlib`` is now tested on macOS and Windows.
- Type annotations have been completed throughout the code base.
