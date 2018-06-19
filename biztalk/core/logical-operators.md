---
title: 論理演算子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8aaceb64-a5a0-462a-a0eb-8352bed999e5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e3b3c187e353babafd86590fdeacdc19fc115b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262074"
---
# <a name="logical-operators"></a>論理演算子
ビジネス ルール フレームワークは、ビジネス ルールを作成する際の論理演算子の AND、OR、および NOT の使用をサポートします。 次の表では、論理演算子について説明します。  
  
|論理演算子|Description|  
|----------------------|-----------------|  
|**AND**|返します**true**に両方のオペランドが評価される場合**true**; を返しますそれ以外の場合**false**です。|  
|**OR**|返します**true**に評価されると、オペランドの 1 つ**true**、それ以外の場合**false**です。|  
|**NOT**|返します**true**にオペランドが評価された場合**false**、それ以外の場合を返します**false**です。|  
  
 オペランドが異なる型である場合は、式の評価の前に、ルール エンジンによって 1 つのパラメーターの型がもう 1 つのパラメーターの型と一致するように変換されるか、両方のパラメーターの型が共通の型に変換されます。  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a>ビジネス ルールで論理演算子を使用するには  
 ビジネス ルールで論理演算子を使用するには、次の手順に従います。  
  
1.  **IF**のビジネス ルール作成ツール ウィンドウを右クリックし、**条件**ノード、および論理式に追加する論理演算子を選択します。  
  
2.  論理演算子を右クリックし、追加する述語または入れ子になった論理演算子を追加します。  
  
## <a name="see-also"></a>参照  
 [算術演算子](../core/arithmetic-operators.md)