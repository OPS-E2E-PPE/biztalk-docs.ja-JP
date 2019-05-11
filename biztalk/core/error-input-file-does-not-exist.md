---
title: エラー - 入力ファイルが存在しない |Microsoft Docs
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
ms.openlocfilehash: 4e825ba6d0046e3be686cd155b5a8892a5ae8b99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388805"
---
# <a name="error---input-file-does-not-exist"></a>エラー - 入力ファイルが存在しません
**エラー コード**  
  
 btm1037  
  
 **説明**  
  
 マップのテスト操作が存在しないため、マップのテスト入力の種類に設定されていない指定した入力インスタンス メッセージ ファイル**インスタンスの生成**します。 ときの値、 **TestMap の入力**マップのプロパティに設定されていない**インスタンスの生成**、既存のインスタンス メッセージ ファイルを指定する必要があります、 **TestMap の入力インスタンス**プロパティをマップします。  
  
 **ユーザーの操作**  
  
 必要に応じて、次のマップのプロパティのどちらかを設定します。  
  
-   **TestMap の入力インスタンス。** ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト** タブで、**プロパティ ページ** ダイアログ ボックス、マップの省略記号 (をクリックします。**...**) の値フィールドのボタン、 **TestMap の入力インスタンス**プロパティ。 使用して、**入力ファイルの選択**ダイアログ ボックスで、既存のインスタンスのメッセージ マップの送信元スキーマに準拠しているファイルを選択します。 値フィールドに直接このファイルのパスを入力する代わりに、 **TestMap の入力インスタンス**プロパティ。  
  
-   **TestMap の入力。** 入力インスタンス メッセージ ファイルを指定することを避けるためには、[ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト**のタブ、**プロパティ ページ**] ダイアログ ボックスの値フィールドに、ドロップダウン リスト、マップ、 **TestMap の入力**プロパティを選択する**インスタンスの生成**します。 ファイルを指定するこの例では、必要があります、 **TestMap の入力インスタンス**プロパティ。