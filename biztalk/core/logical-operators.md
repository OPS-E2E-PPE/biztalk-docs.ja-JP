---
title: 論理演算子 |Microsoft Docs
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
ms.openlocfilehash: 940f9a1c3604108de58a44aa6998dcdd82e86abb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380574"
---
# <a name="logical-operators"></a>論理演算子
ビジネス ルール フレームワークでは、論理 AND、OR を使用し、論理ビジネス ルールの作成に NOT 演算子。 次の表では、論理演算子について説明します。  
  
|論理演算子|説明|  
|----------------------|-----------------|  
|**AND**|返します**true**に両方のオペランドが評価される場合**true**; を返しますそれ以外の場合**false**します。|  
|**OR**|返します**true**に評価されると、オペランドの 1 つ**true**、それ以外の場合を返します**false**。|  
|**NOT**|返します**true**にオペランドが評価された場合**false**、それ以外の場合**false**します。|  
  
 オペランドは、さまざまな種類が、ルール エンジンには、式を評価する前に、他のパラメーターまたは変換型の共通の型に、両方のパラメーターの型に一致するパラメーターのいずれかの型に変換します。  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a>ビジネス ルールで論理演算子を使用するには  
 ビジネス ルールで論理演算子を使用するのにには、次の手順を使用します。  
  
1.  **場合**ビジネス ルール作成ツールのウィンドウを右クリックし、**条件**ノード、および論理式を追加する論理演算子を選択します。  
  
2.  論理演算子を右クリックし、述語または追加する、入れ子になった論理演算子を追加します。  
  
## <a name="see-also"></a>参照  
 [算術演算子](../core/arithmetic-operators.md)