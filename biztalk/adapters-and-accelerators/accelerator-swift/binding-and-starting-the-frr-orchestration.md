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
ms.openlocfilehash: b01386cedbd25148e5ea0ce2ac44fb56e9fe3d03
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987443"
---
# <a name="binding-and-starting-the-frr-orchestration"></a>バインドおよび FRR オーケストレーションを開始します。
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FRR オーケストレーションが展開されたアセンブリ (Microsoft として含まれています。Solutions.FinancialServices.SWIFT.FrrOrchestration)。 このオーケストレーションを開始する必要があります。  
  
 **概要**  
  
 FRR オーケストレーションを開始するには、次の操作を行います。  
  
-   BizTalkServerApplication ホストを設定して FrrOrchestration.FrrMain オーケストレーションをバインドします。  
  
-   FrrOrchestration.FrrMain オーケストレーションを開始します。  
  
### <a name="to-bind-and-start-the-frr-orchestration"></a>バインドして FRR オーケストレーションの開始  
  
1.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、 **BizTalk グループ**、**アプリケーション**、し**BizTalkアプリケーション 1**します。 クリックして**オーケストレーション**します。  
  
2.  オーケストレーション ペインで右クリックし、 **FrrOrchestration.FrrMain**オーケストレーション、およびクリック**プロパティ**します。  
  
3.  [オーケストレーションのプロパティ] ダイアログ ボックスで、**バインド**左側のウィンドウでします。 **ホスト**、 **BizTalkServerApplication**します。 クリックして**適用**、順にクリックします**OK**します。  
  
4.  オーケストレーション ペインで右クリックし、 **FrrMain**オーケストレーション、およびクリック**開始**します。