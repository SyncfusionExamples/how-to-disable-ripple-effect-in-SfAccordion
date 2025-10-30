# how-to-disable-ripple-effect-in-SfAccordion

This repository contains a small .NET MAUI sample that demonstrates how to disable the ripple (touch) effect shown in the header area of Syncfusion's `SfAccordion` control.

The ripple effect is a platform visual feedback applied to interactive header areas. In some designs you may want a static header without the ripple feedback. This sample shows a minimal approach by overriding the Syncfusion theme resource responsible for the header ripple background and setting it to `Transparent`.


## Overview

What this repo does:

- Demonstrates how to disable the ripple effect in `SfAccordion` headers by overriding the theme resource `SfAccordionHeaderRippleBackground`.
- Provides a small `MainPage.xaml` showing several `AccordionItem` entries.
- Keeps the project focused and easy to reuse in other MAUI apps.

Reference: Syncfusion .NET MAUI Accordion documentation — [Getting Started with MAUI Accordion](https://help.syncfusion.com/maui/accordion/getting-started)


## Xaml

The sample achieves this by adding a `SyncfusionThemeDictionary` in the page resources and overriding `SfAccordionHeaderRippleBackground` to `Transparent`. Here is the relevant XAML taken from `MainPage.xaml` in this repository:

```
<ContentPage.Resources>
	<syncTheme:SyncfusionThemeDictionary>
		<syncTheme:SyncfusionThemeDictionary.MergedDictionaries>
			<ResourceDictionary>
				<x:String x:Key="SfAccordionTheme">CustomTheme</x:String>
				<Color x:Key="SfAccordionHeaderRippleBackground">Transparent</Color>
			</ResourceDictionary>
		</syncTheme:SyncfusionThemeDictionary.MergedDictionaries>
	</syncTheme:SyncfusionThemeDictionary>
</ContentPage.Resources>
```

Full `SfAccordion` example from `MainPage.xaml` (shortened for clarity):

```
<syncfusion:SfAccordion>
	<syncfusion:SfAccordion.Items>
		<syncfusion:AccordionItem>
			<syncfusion:AccordionItem.Header>
				<Grid>
					<Label TextColor="#495F6E" Text="Cheese burger" HeightRequest="50" VerticalTextAlignment="Center"/>
				</Grid>
			</syncfusion:AccordionItem.Header>
			<syncfusion:AccordionItem.Content>
				<Grid Padding="10,10,10,10" BackgroundColor="#FFFFFF">
					<Label TextColor="#303030" Text="Hamburger accompanied with melted cheese..." HeightRequest="50" VerticalTextAlignment="Center"/>
				</Grid>
			</syncfusion:AccordionItem.Content>
		</syncfusion:AccordionItem>
		<!-- additional AccordionItems omitted -->
	</syncfusion:SfAccordion.Items>
</syncfusion:SfAccordion>
```

## How it works

Syncfusion controls expose themeable resources which you can override in your resource dictionaries. The `SfAccordionHeaderRippleBackground` resource controls the background brush/color that appears during the header touch ripple. By setting it to `Transparent`, the ripple becomes invisible while the header remains interactive (tapping still expands/collapses the item).

This approach is lightweight and confines the change to the page (or app-level resources, if you prefer). If you want the change to apply across your entire app, move the same resource override to `App.xaml` inside the application's resource dictionary.

##### Conclusion

I hope you enjoyed learning about how to disable the Ripple effect in Header of .NET MAUI Accordion (SfAccordion).

You can refer to our [.NET MAUI Accordion](https://www.syncfusion.com/maui-controls/maui-accordion) feature tour page to know about its other groundbreaking feature representations. You can also explore our [.NET MAUI Accordion documentation](https://help.syncfusion.com/maui/accordion/getting-started) to understand how to present and manipulate data.

For current customers, you can check out our components from the [License and Downloads](https://www.syncfusion.com/account/login) page. If you are new to Syncfusion, you can try our 30-day [free trial](https://www.syncfusion.com/downloads/maui) to check out our other controls.

If you have any queries or require clarifications, please let us know in the comments section below. You can also contact us through our [support forums](https://www.syncfusion.com/forums/), [Direct-Trac](https://support.syncfusion.com/create), or [feedback portal](https://www.syncfusion.com/feedback/maui?control=sflistview). We are always happy to assist you!
