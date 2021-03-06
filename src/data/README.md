### How To Update Product Cards
Tutorial on how to update all product card content. The cards are stored in an array of objects with key value pairs that map to component props as well as some display logic. 

**Example Card Information**
```node 
    {
        id: 'outsideMotionSensorRight',
        roomForMobileCard: ADI_ROOM_FILTER.NODISPLAYONMOBILE,
        arrowDirection: ArrowDirection.RIGHT,
        productImage:
            'data:image/jpeg;base64,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',

        productImageAltText: 'Tv',
        productMetaLink: '/',
        copy: `Smart TVs are connected and Internet-ready. Most TVs available on the market now have smart capabilities, allowing customers to enjoy a wider range of entertainment stream movies, shows and music from dozens of channels, browse the web or connect with other entertainment devices.`,
        productMetaLinkText: 'View Product',
        productMetaName: 'SONY 65 LED 4K ULTRA HD SMART TV',
        shopMoreBtn: 'SHOP ALL HOME HUBS',
        shopMoreBtnLink: '/',
        title: 'outsideMotionSensorRight',
    }
```

id: The CSS ID used to apply proper card and pulse specific styling information.

roomForMobileCard: List of ENUMs for use on mobile only. These values correspond to what slider the card should show up on. For the case of roofs and motion sensors the mockup only had 1 product pulser and image showing up so there is a special enum called ```NODISPLAYONMOBILE``` that will exclude it from rendering.

productImage: It is advised to not embed images directly into the components as that will likely increase page load time. The best option is to serve these image assets via a CDN, and then just call the CDN link as the source.

The rest of the keys are self explanatory to fill out as the correspond directly to the placeholder text in the live production version.