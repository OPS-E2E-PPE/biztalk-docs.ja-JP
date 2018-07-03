---
title: エラー - ネストされたクラス名の競合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.nestedClassNameCollision
ms.assetid: dd636d25-d0c1-41be-a2ba-b38ea97b973d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 856841093c37848924dc6e9b6d160186e03ad304
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003331"
---
# <a name="error---nested-class-name-collision"></a>エラー - ネストされたクラス名の競合
**エラー コード**  

 BEC2017  

 **説明**  

 **型名**このスキーマのプロパティが同じである見つかりました、 **RootNode TypeName**のスキーマのルート ノードのいずれかのプロパティ。 C# では同じ名前のクラスを入れ子にすることが許可されないため、この状態が原因でエラーが発生します。  

 **ユーザーの操作**  

 名前の競合を避けるために、関連するプロパティ値の 1 つまたは両方を変更する必要があります。 次のいずれかの操作を行います。  

- Microsoft では、関連するスキーマ ファイルを選択します。[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで、し、[プロパティ] ウィンドウで次のように変更します。、**型名**プロパティを一意の有効な値にします。  

   \- または -  

- 対象のルート ノードを選択し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、変更、 **RootNode TypeName**プロパティを一意の有効な値にします。
