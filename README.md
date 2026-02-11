This project demonstrates Android UI development concepts including fragment navigation, implementing Figma designs into XML layouts, and handling complex scrolling using NestedScrollView and HorizontalScrollView within a CoordinatorLayout structure.

# Features
1.Fragment-based navigation
2.Figma design implementation in Android XML
3.Vertical scrolling using NestedScrollView
4.Horizontal scrolling using HorizontalScrollView
5.AppBarLayout with scroll behavior
6.BottomAppBar integration
7.Proper layout measurement handling

# Lessons Learned – Android Layout & Scrolling

1️⃣ ScrollView / NestedScrollView Rules:
Never use layout_height="match_parent" for children inside ScrollView or NestedScrollView.
Always use layout_height="wrap_content".
ScrollView measures children with unspecified height, so match_parent causes layout issues.

2️⃣ HorizontalScrollView Rules:
Child width must be wrap_content, not match_parent.
Horizontal scrolling only works if content width exceeds screen width.
Using match_parent prevents proper horizontal scrolling.

3️⃣ CoordinatorLayout + AppBarLayout:
When using AppBarLayout with scrolling content, always add:
**app:layout_behavior="@string/appbar_scrolling_view_behavior"**
to the scrolling view.
This connects the scrolling content with the Toolbar behavior.

4️⃣ Layout Hierarchy Matters
Different parent layouts measure children differently:
**Parent_Layout**	           **Important_Rule**
ScrollView          	Child height → wrap_content
HorizontalScrollView	Child width → wrap_content
CoordinatorLayout	    Requires layout_behavior for scrolling
LinearLayout	        match_parent usually safe

Understanding the parent layout is key to fixing UI bugs.
