---
title: エラー - 入力ファイルが存在しません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.inputFileDoesNotExist
ms.assetid: 6cd2f076-6c3e-46e3-8be4-dad2d9b95d37
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a14221857ebb567020a52c2ff0939b506d28937
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241802"
---
# <a name="error---input-file-does-not-exist"></a>エラー - 入力ファイルが存在しません
**エラー コード**  
  
 btm1037  
  
 **説明**  
  
 マップのテスト操作が存在しないと、マップのテストの入力の型に設定されていない指定した入力インスタンス メッセージ ファイル**インスタンスの生成**です。 ときの値、 **TestMap の入力**マップのプロパティに設定されていない**インスタンスの生成**、既存のインスタンス メッセージ ファイルを指定する必要があります、 **TestMap の入力インスタンス**プロパティをマップします。  
  
 **ユーザーの操作**  
  
 適宜、以下のマップ プロパティのいずれかを設定します。  
  
-   **TestMap の入力インスタンス。** ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト** タブで、**プロパティ ページ** ダイアログ ボックス、マップをクリックして、省略記号 (**...**) の値フィールドのボタン、 **TestMap の入力インスタンス**プロパティです。 使用して、**入力ファイルの選択**ダイアログ ボックスで、既存のインスタンス メッセージ マップの送信元スキーマに準拠しているファイルを選択します。 値フィールドに直接このファイルのパスを入力する代わりに、 **TestMap の入力インスタンス**プロパティです。  
  
-   **TestMap の入力します。** 入力インスタンス メッセージ ファイルを指定することを回避するのには、ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト**のタブ、**プロパティ ページ**の値フィールドに使用して、ドロップダウン リスト、マップのダイアログ ボックス、 **TestMap の入力**プロパティを選択する**インスタンスの生成**です。 ここでは、必要がありますいないファイルを指定するため、 **TestMap の入力インスタンス**プロパティです。