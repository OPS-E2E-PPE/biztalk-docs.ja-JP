---
title: "中断図形を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Suspend shapes
- Suspend shape [Orchestration Designer], literal strings
- Suspend shape [Orchestration Designer], configuring
- Suspend shape [Orchestration Designer]
- atomic transactions, Suspend shape [Orchestration Designer]
- Suspend shape [Orchestration Designer], atomic transactions
- Suspend shape [Orchestration Designer], about Suspend shape
ms.assetid: 62fbb6d4-78d2-4671-84bb-909cbf6b0ec3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c846001b5a2b39a4e23e0d06ed56fb91c8863832
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-suspend-shape"></a>中断図形を構成する方法
![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")  
中断図形  
  
 オーケストレーション インスタンスが中断されると、エラーがログに記録されます。 管理者が状況を診断しやすいよう、このエラーに添えるメッセージ文字列を指定できます。  
  
 すべてのオーケストレーション インスタンスの状態情報が保存され、管理者は、オーケストレーション インスタンスを再開する場合に再開します。  
  
> [!NOTE]
>  場合、 **Suspend**同期的に呼び出されたオーケストレーションに図形が存在する (と同様、**呼び出す**図形) 別のオーケストレーションによって、入れ子になったインスタンスすべてを囲んでいるオーケストレーション インスタンスは、中断されます。  
  
> [!NOTE]
>  配置することはできません、 **Suspend**をアトミック トランザクション内部の図形です。  
  
### <a name="to-configure-a-suspend-shape"></a>中断図形を構成するには  
  
-   使用することができます、**エラー メッセージ**プロパティをテキストを指定するときにログに記録、 **Suspend**図形が検出されました。 このテキストはリテラル文字列、またはに評価される式が適用される場合があります、 **System.String**です。  
  
    > [!CAUTION]
    >  リテラル文字列を入力する場合は、二重引用符で囲む必要があります。