---
title: エラー - マップのテスト用の入力が有効ではありません |Microsoft Docs
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
ms.openlocfilehash: 81aca2f6d941f281a2a720250714c76798762e6b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346572"
---
# <a name="error---test-map-inputs-not-valid"></a>エラー - マップのテスト用の入力が無効です。
**エラー コード**  
  
 btm1036  
  
 **説明**  
  
 マップのテスト操作の入力インスタンス メッセージ ファイルが指定されていないと、TestMap の入力の種類に設定されていない**インスタンスの生成**します。 ときの値、 **TestMap の入力**マップのプロパティに設定されていない**インスタンスの生成**のインスタンス メッセージ ファイルを指定する必要があります、 **TestMap の入力インスタンス**マッププロパティ。  
  
 **ユーザーの操作**  
  
 必要に応じて、次のマップのプロパティのどちらかを設定します。  
  
-   **TestMap の入力インスタンス。** ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト** タブで、**プロパティ ページ** ダイアログ ボックス、マップの省略記号 (をクリックします。**...**) の値フィールドのボタン、 **TestMap の入力インスタンス**プロパティ。 使用して、**入力ファイルの選択** ダイアログ ボックスで、インスタンス メッセージ マップの送信元スキーマに準拠しているファイルを選択します。 値フィールドに直接このファイルのパスを入力する代わりに、 **TestMap の入力インスタンス**プロパティ。  
  
-   **TestMap の入力。** 入力インスタンス メッセージ ファイルを指定することを避けるためには、ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト** タブで、**プロパティ ページ** ダイアログ ボックスの値フィールドに、ドロップダウン リスト、マップ、 **TestMap の入力**プロパティを選択する**インスタンスの生成**します。 ファイルを指定するこの例では、必要があります、 **TestMap の入力インスタンス**プロパティ。