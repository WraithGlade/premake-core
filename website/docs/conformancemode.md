`conformancemode` is used to control whether or not MS Visual Studio (and perhaps other build systems?) will try harder to adhere to the language standard you've specified when building the project. In other words, it is used to control *some* aspects of whether you prefer (1) better portability across compilers and target systems or (2) more features and permissiveness.

```lua
conformancemode(bool)
```

### Parameters ###

`bool` can be either `true` or `false`. Parentheses are required here in Lua, since the parameter is not a string or table. 

If `conformancemode` is set to `true` then the generated project will have its standard conformance flag enabled, thereby increasing the chances that you won't accidentally write code that can't be compiled outside of the generated build system's ecosystem during development on your current platform. This gives you better portability but reduces what features are available to you.

In contrast, if `conformancemode` is set to false, then you get the opposite tradeoff: worse cross-platform compatibility but more features.

## Applies To ###

The `config` scope.

### Availability ###

Premake 5.0.0 beta 1 or later.

### Examples ###

```lua
conformancemode(true)   -- better for cross-platform development
conformancemode(false)  -- more platform-specific build/compiler features
```

