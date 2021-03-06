UPGRADE FROM 3.2 to 3.3
=======================

ClassLoader
-----------

 * The component is deprecated and will be removed in 4.0. Use Composer instead.

Debug
-----

 * The `ContextErrorException` class is deprecated. `\ErrorException` will be used instead in 4.0.

DependencyInjection
-------------------

 * Autowiring-types have been deprecated, use aliases instead.

   Before:

   ```xml
   <service id="annotations.reader" class="Doctrine\Common\Annotations\AnnotationReader" public="false">
       <autowiring-type>Doctrine\Common\Annotations\Reader</autowiring-type>
   </service>
   ```

   After:

   ```xml
   <service id="annotations.reader" class="Doctrine\Common\Annotations\AnnotationReader" public="false" />
   <service id="Doctrine\Common\Annotations\Reader" alias="annotations.reader" public="false" />
   ```

 * The `Reference` and `Alias` classes do not make service identifiers lowercase anymore.

 * Case insensitivity of service identifiers is deprecated and will be removed in 4.0.

 * Using the `PhpDumper` with an uncompiled `ContainerBuilder` is deprecated and
   will not be supported anymore in 4.0.

 * The `DefinitionDecorator` class is deprecated and will be removed in 4.0, use
   the `ChildDefinition` class instead.

EventDispatcher
---------------

 * The `ContainerAwareEventDispatcher` class has been deprecated.
   Use `EventDispatcher` with closure-proxy injection instead.

Finder
------

 * The `ExceptionInterface` has been deprecated and will be removed in 4.0.

FrameworkBundle
---------------

 * The `Symfony\Bundle\FrameworkBundle\DependencyInjection\Compiler\AddConsoleCommandPass` has been deprecated. Use `Symfony\Component\Console\DependencyInjection\AddConsoleCommandPass` instead.

HttpKernel
-----------

 * The `Psr6CacheClearer::addPool()` method has been deprecated. Pass an array of pools indexed
   by name to the constructor instead.

Process
-------

 * The `ProcessUtils::escapeArgument()` method has been deprecated, use a command line array or give env vars to the `Process::start/run()` method instead.

 * Not inheriting environment variables is deprecated.

 * Configuring `proc_open()` options is deprecated.

 * Configuring Windows and sigchild compatibility is deprecated - they will be always enabled in 4.0.

Security
--------

 * The `RoleInterface` has been deprecated. Extend the `Symfony\Component\Security\Core\Role\Role`
   class in your custom role implementations instead.

SecurityBundle
--------------

 * The `FirewallContext::getContext()` method has been deprecated and will be removed in 4.0.
   Use the `getListeners()` method instead.

 * The `FirewallMap::$map` and `$container` properties have been deprecated and will be removed in 4.0.

TwigBridge
----------

 * The `TwigRendererEngine::setEnvironment()` method has been deprecated and will be removed
   in 4.0. Pass the Twig Environment as second argument of the constructor instead.

Workflow
--------

 * Deprecated class name support in `WorkflowRegistry::add()` as second parameter.
   Wrap the class name in an instance of ClassInstanceSupportStrategy instead.

Yaml
----

 * The constructor arguments `$offset`, `$totalNumberOfLines` and
   `$skippedLineNumbers` of the `Parser` class are deprecated and will be
   removed in 4.0
