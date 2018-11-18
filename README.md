<p align="center">
    <a href="https://github.com/yiisoft" target="_blank">
        <img src="https://avatars0.githubusercontent.com/u/993323" height="100px">
    </a>
    <h1 align="center">Yii2 Active Record Behaviors</h1>
    <br>
</p>

## Installation

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Install

```
composer require m-comscience/yii2-core-multi-value-behavior
```

## Usage

model
```php
use mcomscience\behaviors\CoreMultiValueBehavior;

public function behaviors()
{
    return [
        [
            'class' => CoreMultiValueBehavior::className(),
            'attributes' => [
                ActiveRecord::EVENT_BEFORE_INSERT => ['attribute1'],
                ActiveRecord::EVENT_BEFORE_UPDATE => ['attribute2'],
            ],
            'value' => function ($event) {
                return $event->sender[$event->data];
            },
        ],
    ];
}
```