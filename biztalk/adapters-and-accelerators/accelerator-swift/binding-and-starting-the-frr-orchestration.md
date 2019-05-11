---
title: バインドと FRR オーケストレーションの開始 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, binding orchestrations
- FRR, starting orchestrations
- bindings, orchestrations
- orchestrations, bindings
ms.assetid: b74a0116-e98b-4fec-b386-710ce421a1e2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1189b7db68cc0894725a98887fc82d30dde5a33
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378978"
---
# <a name="binding-and-starting-the-frr-orchestration"></a>バインドおよび FRR オーケストレーションを開始します。
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR オーケストレーションが展開されたアセンブリ (Microsoft として含まれています。Solutions.FinancialServices.SWIFT.FrrOrchestration)。 このオーケストレーションを開始する必要があります。  
  
 **まとめ**  
  
 FRR オーケストレーションを開始するには、次の操作を行います。  
  
-   BizTalkServerApplication ホストを設定して FrrOrchestration.FrrMain オーケストレーションをバインドします。  
  
-   FrrOrchestration.FrrMain オーケストレーションを開始します。  
  
### <a name="to-bind-and-start-the-frr-orchestration"></a>バインドして FRR オーケストレーションの開始  
  
1.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、 **BizTalk グループ**、**アプリケーション**、し**BizTalkアプリケーション 1**します。 クリックして**オーケストレーション**します。  
  
2.  オーケストレーション ペインで右クリックし、 **FrrOrchestration.FrrMain**オーケストレーション、およびクリック**プロパティ**します。  
  
3.  [オーケストレーションのプロパティ] ダイアログ ボックスで、**バインド**左側のウィンドウでします。 **ホスト**、 **BizTalkServerApplication**します。 クリックして**適用**、順にクリックします**OK**します。  
  
4.  オーケストレーション ペインで右クリックし、 **FrrMain**オーケストレーション、およびクリック**開始**します。