PHP 以前的版本有扩展 apc，apc缓存分为系统缓存和用户缓存。
php5.5以后，opcache将代替apc做为php加速的位置，也就是代替其系统缓存的位置。
用户缓存功能独立出来，开启新的组件，这个组件名称叫做apcu。
所以这两个扩展不冲突。