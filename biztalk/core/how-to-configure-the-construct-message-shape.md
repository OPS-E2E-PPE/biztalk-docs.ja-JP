---
title: メッセージの構築図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Construct Message shape [Orchestration Designer], configuring
- Construct Message shape [Orchestration Designer]
- configuring [Orchestration Designer], Construct Message shapes
- Construct Message shape [Orchestration Designer], about Construct Message shape
ms.assetid: 8d052b4e-0873-4102-9462-6604423d0524
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a16900b1ee5c98c059b01f92a770f845330b9ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386168"
---
# <a name="how-to-configure-the-construct-message-shape"></a>メッセージの構築図形を構成する方法
![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")  
メッセージの構築図形  
  
 を構築するメッセージ変数を指定し、メッセージまたはメッセージの部分の割り当てを行います。 特定のメッセージに対するすべての割り当ては、同じメッセージの構築図形内で実行する必要があります。  
  
 既に構築されたメッセージ プロパティを変更する場合: が受信されたメッセージなど、2 番目の最初の割り当てと、新しいメッセージ インスタンスのプロパティを変更して新しいメッセージ インスタンスを構築する必要があります構築と変更の両方に同じメッセージの構築図形内で発生します。  
  
### <a name="to-configure-a-construct-message-shape"></a>メッセージの構築図形を構成するには  
  
1.  [プロパティ] ウィンドウで使用して、**構築メッセージ**はこの図形がメッセージを指定するプロパティを構築します。  
  
2.  追加し、1 つ以上構成**変換**または**メッセージの割り当て**図形内で、**メッセージの構築図形**します。