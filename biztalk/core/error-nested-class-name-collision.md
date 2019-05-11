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
ms.openlocfilehash: 37edc5012d2298e9516e766743b58f7d5448cf6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388619"
---
# <a name="error---nested-class-name-collision"></a>エラー - ネストされたクラス名の競合
**エラー コード**  

 BEC2017  

 **説明**  

 **型名**このスキーマのプロパティが同じである見つかりました、 **RootNode TypeName**のスキーマのルート ノードのいずれかのプロパティ。 C# では入れ子になったクラスと同じ名前です。そのためこの条件では、エラーが発生します。  

 **ユーザーの操作**  

 名前の競合を避けるために、関連するプロパティ値の一方または両方を変更する必要があります。 次のいずれかの操作を行います。  

- Microsoft では、関連するスキーマ ファイルを選択します。[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで、し、[プロパティ] ウィンドウで次のように変更します。、**型名**プロパティを一意の有効な値にします。  

   \- - または -  

- 対象のルート ノードを選択し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、変更、 **RootNode TypeName**プロパティを一意の有効な値にします。
