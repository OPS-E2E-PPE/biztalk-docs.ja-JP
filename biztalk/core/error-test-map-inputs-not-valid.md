---
title: エラー - マップのテスト用の入力が有効ではありません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.testMapInputsNotValid
ms.assetid: d885d366-92a3-4d2a-8e2b-58e06960864f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 912b70bcd74180a20d54da11dffdab79f54fc5b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---test-map-inputs-not-valid"></a>エラー - マップのテスト用の入力が有効ではありません。
**エラー コード**  
  
 btm1036  
  
 **説明**  
  
 マップのテスト操作は、入力インスタンス メッセージ ファイルが指定されていないと、TestMap の入力の型に設定されていない**インスタンスの生成**です。 ときの値、 **TestMap の入力**マップのプロパティに設定されていない**インスタンスの生成**のインスタンス メッセージ ファイルを指定する必要があります、 **TestMap の入力インスタンス**マッププロパティ。  
  
 **ユーザーの操作**  
  
 適宜、以下のマップ プロパティのいずれかを設定します。  
  
-   **TestMap の入力インスタンス。** ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト** タブで、**プロパティ ページ** ダイアログ ボックス、マップをクリックして、省略記号 (**...**) の値フィールドのボタン、 **TestMap の入力インスタンス**プロパティです。 使用して、**入力ファイルの選択**ダイアログ ボックスで、インスタンス メッセージ マップの送信元スキーマに準拠しているファイルを選択します。 値フィールドに直接このファイルのパスを入力する代わりに、 **TestMap の入力インスタンス**プロパティです。  
  
-   **TestMap の入力します。** 入力インスタンス メッセージ ファイルを指定することを回避するのには、ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト** タブで、**プロパティ ページ**の値フィールドに使用して、ドロップダウン リスト、マップのダイアログ ボックス、 **TestMap の入力**プロパティを選択する**インスタンスの生成**です。 ここでは、必要がありますいないファイルを指定するため、 **TestMap の入力インスタンス**プロパティです。