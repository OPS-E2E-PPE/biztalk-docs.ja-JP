---
title: バインドおよび FRR オーケストレーションを開始 |Microsoft ドキュメント
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
ms.openlocfilehash: 81cf116fc03a8f2d898752a077e8347fd395a4a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209058"
---
# <a name="binding-and-starting-the-frr-orchestration"></a>バインドおよび FRR オーケストレーションを開始します。
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]展開されたアセンブリとして FRR オーケストレーションが含まれています ([!INCLUDE[btsCoName](../../includes/btsconame-md.md)]です。Solutions.FinancialServices.SWIFT.FrrOrchestration)。 このオーケストレーションを開始する必要があります。  
  
 **概要**  
  
 FRR オーケストレーションを開始するには、次の操作を行います。  
  
-   BizTalkServerApplication ホストを設定して FrrOrchestration.FrrMain オーケストレーションをバインドします。  
  
-   FrrOrchestration.FrrMain オーケストレーションを開始します。  
  
### <a name="to-bind-and-start-the-frr-orchestration"></a>バインドして FRR オーケストレーションの開始  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、 **BizTalk グループ**、**アプリケーション**、し**BizTalkアプリケーション 1**です。 をクリックして**オーケストレーション**です。  
  
2.  オーケストレーション ペインで右クリックし、 **FrrOrchestration.FrrMain**オーケストレーション、およびクリック**プロパティ**です。  
  
3.  [オーケストレーションのプロパティ] ダイアログ ボックスで、**バインド**左側のウィンドウでします。 **ホスト** **BizTalkServerApplication**です。 をクリックして**適用**、順にクリック**OK**です。  
  
4.  オーケストレーション ペインで右クリックし、 **FrrMain**オーケストレーション、およびクリック**開始**です。