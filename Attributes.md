## Supported attributes

|Attributes for Flexbox Layout                | Description       |
| ----------------------- |:-----------------:|
|flexDirection            | Defines the direction of the main axis and the perpendicular cross axis. |
|flexWrap                 | Determines whether the flex items are forced in a single line or can be flowed into multiple lines. If set to multiple lines, it also defines the cross-axis which determines the direction new lines are stacked in.|
|justifyContent           | Defines the alignment along the main axis, and helps use empty space if there is any left.  |
|alignItems               | Similar to justifyContent, but defines alignment along the cross axis rather than the main axis. Also helps use empty space.|

| Attribute for Flexbox Children                | Description       |
| ----------------------- |:-----------------:|
| layout_order            | Determines how the ordering of the children views are laid out. |
| layout_flexGrow         | Determines how much the child will grow if there is positive free space. |
| layout_flexShrink       | Determines how much the child will shrink if there is negative free space. |
| layout_alignSelf        | This attribute determines the alignment along the cross axis (perpendicular to the main axis). |
| layout_flexBasisPercent | Determines the size of the child based on a ratio reltaive to the parent.|
| layout_minWidth         | Determines the minimum width of a child of a flexbox layout |
| layout_minHeight        | Determines the minimum height of a child of a flexbox layout |
| layout_maxWidth         | Determines the maximum width of a child of a flexbox layout |
| layout_maxHeight        | Determines the maximum height of a child of a flexbox layout |
| layout_wrapBefore       | Determines whether a child will be the first item of a flex line. |

## Attributes for Flexbox Layout  

#### flexDirection
  * The direction children items are placed inside the Flexbox layout, it determines the
  direction of the main axis (and the cross axis, perpendicular to the main axis).
  Possible values are:
    * row (default)
    * row_reverse
    * column
    * column_reverse

#### flexWrap
  * This attribute controls whether the flex container is single-line or multi-line, and the
  direction of the cross axis. Possible values are:
    * nowrap (default)
    * wrap
    * wrap_reverse

#### justifyContent
  * This attribute controls the alignment along the main axis. Possible values are:
    * flex_start (default)
    * flex_end
    * center
    * space_between
    * space_around


#### alignItems
  * This attribute controls the alignment along the cross axis. Possible values are:
    * stretch (default)
    * flex_start
    * flex_end
    * center
    * baseline


#### alignContent
  * This attribute controls the alignment of the flex lines in the flex container. Possible values
  are:
    * stretch (default)
    * flex_start
    * flex_end
    * center
    * space_between
    * space_around


## Attributes for the children of a FlexboxLayout.

#### layout_order 
(integer)
  * This attribute can change how the ordering of the children views are laid out.
  By default, children are displayed and laid out in the same order as they appear in the
  layout XML. If not specified, `1` is set as a default value.

#### layout_flexGrow 
(float)
  * This attribute determines how much this child will grow if positive free space is
  distributed relative to the rest of other flex items included in the same flex line.
  If not specified, `0` is set as a default value.

#### layout_flexShrink 
(float)
  * This attribute determines how much this child will shrink if negative free space is
  distributed relative to the rest of other flex items included in the same flex line.
  If not specified, `1` is set as a default value.

#### layout_alignSelf 
  * This attribute determines the alignment along the cross axis (perpendicular to the
  main axis). The alignment in the same direction can be determined by the
  `alignItems` in the parent, but if this is set to other than
  `auto`, the cross axis alignment is overridden for this child. Possible values are:
    * auto (default)
    * flex_start
    * flex_end
    * center
    * baseline
    * stretch

#### layout_flexBasisPercent 
(fraction)
  * The initial flex item length in a fraction format relative to its parent.
  The initial main size of this child view is trying to be expanded as the specified
  fraction against the parent main size.
  If this value is set, the length specified from `layout_width`
  (or `layout_height`) is overridden by the calculated value from this attribute.
  This attribute is only effective when the parent's length is definite (MeasureSpec mode is
  `MeasureSpec.EXACTLY`). The default value is `-1`, which means not set.

#### layout_minWidth 
(dimension)
  * This attributes imposes a minimum width constraint for the children of FlexboxLayout.
  A child view won't be shrank less than the value of these attributes (varies based on the
  `flexDirection` attribute as to which attribute imposes the size constraint along the
  main axis) regardless of the `layout_flexShrink` attribute.

#### layout_minHeight 
(dimension)
  * This attributes imposes a minimum height constraint for the children of FlexboxLayout.
  A child view won't be shrank less than the value of these attributes (varies based on the
  `flexDirection` attribute as to which attribute imposes the size constraint along the
  main axis) regardless of the `layout_flexShrink` attribute.


#### layout_maxWidth  
(dimension)
  * This attributes impose maximum width constraint for the children of FlexboxLayout.
  A child view won't be expanded more than the value of these attributes (varies based on the
  `flexDirection` attribute as to which attribute imposes the size constraint along the
  main axis) regardless of the `layout_flexGrow` attribute.
  
#### layout_maxHeight 
(dimension)
  * This attributes impose maximum height constraint for the children of FlexboxLayout.
  A child view won't be expanded more than the value of these attributes (varies based on the
  `flexDirection` attribute as to which attribute imposes the size constraint along the
  main axis) regardless of the `layout_flexGrow` attribute.
  
#### layout_wrapBefore 
(boolean)
  * This attribute forces a flex line wrapping, the default value is `false`. 
  i.e. if this is set to `true` for a
  flex item, the item will become the first item of a flex line. (A wrapping happens
  regardless of the flex items being processed in the the previous flex line)
  This attribute is ignored if the `flex_wrap` attribute is set to `nowrap`.
  The equivalent attribute isn't defined in the original CSS Flexible Box Module
  specification, but having this attribute is useful for Android developers to flatten
  the layouts when building a grid like layout or for a situation where developers want
  to put a new flex line to make a semantic difference from the previous one, etc.
