---
title: "エラー - 入れ子になったクラス、名前の衝突 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.nestedClassNameCollision
ms.assetid: dd636d25-d0c1-41be-a2ba-b38ea97b973d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4a9fa7a9f57088b3fb93e2eb6024e9b6aad49c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---nested-class-name-collision"></a>エラー - 入れ子になったクラス名の競合
**エラー コード**  
  
 BEC2017  
  
 **説明**  
  
 **型名**と同じであるこのスキーマのプロパティが見つかりました、 **RootNode TypeName**スキーマのルート ノードのいずれかのプロパティです。 C# では同じ名前のクラスを入れ子にすることが許可されないため、この状態が原因でエラーが発生します。  
  
 **ユーザーの操作**  
  
 名前の競合を避けるために、関連するプロパティ値の 1 つまたは両方を変更する必要があります。 次のいずれかの操作を行います。  
  
-   Microsoft では、関連するスキーマ ファイルを選択して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで、し、[プロパティ] ウィンドウで次のように変更します。、**型名**プロパティを一意の有効な値にします。  
  
     \- - または -  
  
-   対象のルート ノードを選択し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで変更、 **RootNode TypeName**プロパティを一意の有効な値にします。