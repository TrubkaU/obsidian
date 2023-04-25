Hilt and Dagger is a [[DI]] frameworks

Hilt provides pre-set scopes:
1. Application, Activity, Fragment, Service, View 
2. Hilt provides @AndroidEntryPoint point, that will allow injecting dependencies into the class by the @Inject annotation
3. Hilt supports the Injection for ViewModule
4. Hilt allows mocking the dependencies better for Espresso tests





Hilt possible to use in multimodule projects where all modules are the regular android library modules, but for the [[FeatureModlules]] it is impossible.

Instead of use the Hilt in FeatureModules, you can use the Dagger together with Hilt.

