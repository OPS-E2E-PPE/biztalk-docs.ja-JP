---
title: "メッセージの構築図形を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Construct Message shape [Orchestration Designer], configuring
- Construct Message shape [Orchestration Designer]
- configuring [Orchestration Designer], Construct Message shapes
- Construct Message shape [Orchestration Designer], about Construct Message shape
ms.assetid: 8d052b4e-0873-4102-9462-6604423d0524
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07b73e7fe62463767894808d7e95f12cf963e4dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-construct-message-shape"></a>メッセージの構築図形を構成する方法
![](../core/media/ebiz-orch-constructmsg.gif "ebiz_orch_constructmsg")  
メッセージの構築図形  
  
 さらに、構築するメッセージ変数を指定して、メッセージまたはメッセージの部分に割り当てます。 特定のメッセージに対するすべての割り当ては、同じメッセージの構築図形内で行う必要があります。  
  
 既に構築されたメッセージのプロパティを変更する場合: が受信されたメッセージなど、2 番目に最初を割り当てる場合や、新しいメッセージ インスタンスのプロパティを変更して、新しいメッセージ インスタンスを構築する必要があります構築と変更の両方に同じメッセージの構築図形内で発生します。  
  
### <a name="to-configure-a-construct-message-shape"></a>メッセージの構築図形を構成するには  
  
1.  [プロパティ] ウィンドウで使用して、**構築メッセージ**するこの図形がメッセージを指定するプロパティが構築されます。  
  
2.  追加して 1 つまたは複数を構成する**変換**または**メッセージの割り当て**図形の内側、**メッセージの構築図形**です。