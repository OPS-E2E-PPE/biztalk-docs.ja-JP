---
title: 中断図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a4a60bfc2d5a98d407e917e0271a9987e88c0bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385953"
---
# <a name="how-to-configure-the-suspend-shape"></a>中断図形を構成する方法
![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")  
中断図形  
  
 オーケストレーション インスタンスが中断されると、エラーが記録されます。 管理者の状況を診断に役立つエラーに添えるメッセージ文字列を指定することができます。  
  
 すべてのオーケストレーション インスタンスの状態情報は保存され、管理者が、オーケストレーション インスタンスを再開する場合に再開します。  
  
> [!NOTE]
>  場合、**中断**が同期的に呼び出されたオーケストレーションに図形が存在します (と同様、**呼び出す**図形) 別のオーケストレーションによって、入れ子になったインスタンスとすべてを囲んでいるオーケストレーション インスタンスが、中断されます。  
  
> [!NOTE]
>  配置することはできません、 **Suspend**アトミックのトランザクション内の図形。  
  
### <a name="to-configure-a-suspend-shape"></a>中断図形を構成するには  
  
-   使用することができます、**エラー メッセージ**プロパティにテキストを指定するときにログに記録、 **Suspend**図形が検出されました。 このテキスト リテラル文字列の場合、またはに評価される式が適用される場合があります、 **System.String**します。  
  
    > [!CAUTION]
    >  リテラル文字列を入力する場合は、引用符で囲む必要があります。