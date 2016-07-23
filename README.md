<ol>
<?php foreach ($this->getItems() as $_item): ?>
    <li class="control">
        <?php if ($_item->getCount() > 0): ?>
            <form>
                <span class="check-box">
                    <input type="checkbox" name="vehicle" style="margin: 0 0 0 0 ;" onclick='window.location.assign("<?php echo $this->urlEscape($_item->getUrl()) ?>")'/>
                </span>
                <a href="<?php echo $this->urlEscape($_item->getUrl()) ?>">
                    <?php echo $_item->getLabel() ?>
                    <?php if ($this->shouldDisplayProductCount()): ?>
                    <span style="color: #ffc100; padding: 0 0 3px;">(<?php echo $_item->getCount() ?>)</span>
                    <?php endif; ?>
                </a>
            </form>
        <?php else: ?>
            <form>
                <span class="check-box">
                    <input type="checkbox" name="vehicle" onclick='window.location.assign("<?php echo $this->urlEscape($_item->getUrl()) ?>")'/>
                </span>
                <span>
                    <?php echo $_item->getLabel(); ?>
                    <?php if ($this->shouldDisplayProductCount()): ?>
                        <span class="count" style="color: #ffc100; padding: 0 0 3px;">(<?php echo $_item->getCount() ?>)</span>
                    <?php endif; ?>
                </span>
            </form>
        <?php endif; ?>
    </li>
<?php endforeach ?>
</ol>
