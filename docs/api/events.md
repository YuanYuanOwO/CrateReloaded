# Getting Started

CrateReloaded has a series of different events to allow you to change the behavior of the plugin. 
In this article, we will be going over one example to send a custom message when a player opens a crate.
This article assumes that you already have a plugin setup.

### Create the listener

```
public class CrateListener {

  @EventHandler(priority = EventPriority.HIGHEST)
  public void onCrateOpen(CrateInteractEvent e) {
    // Stop if it the player is not opening a crate
    if (event.isCancelled() || event.getAction() != CrateAction.OPEN) {
      return;
    }
    
    // This is now sent to the player who is opening the crate
    Messenger.tell(event.getPlayer(), "An event is called!");
  }
}

### Register the listener

```
Bukkit.getPlugin().getServer().getPluginManager().registerEvents(new CrateListener(), getPlugin());
```


## Next steps

If you think this tutorial is enough, you may want to read the [API documentation](https://hazebyte.github.io/CrateReloadedAPI/).
For support, please send us a message in [Github](https://github.com/Hazebyte/CrateReloadedAPI/issues) or [Discord](https://discord.gg/0srgnnU1nbB8wMML).
