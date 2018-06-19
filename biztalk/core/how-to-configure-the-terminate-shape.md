---
title: 終了図形を構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Terminate shape [Orchestration Designer], about Terminate shape
- Terminate shape [Orchestration Designer], literal strings
- configuring [Orchestration Designer], Terminate shapes
- Terminate shape [Orchestration Designer], configuring
- Terminate shape [Orchestration Designer]
ms.assetid: 2c4f2c94-2bab-4af3-8954-7275696ca147
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a5eb4867970c6acafc8903eb474b67541d22764
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247930"
---
# <a name="how-to-configure-the-terminate-shape"></a>終了図形を構成する方法
![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")  
終了図形  
  
 終了図形は、オーケストレーション インスタンスを終了するために使用します。 [グループ ハブ] ページからの出力で表示する際に図形に添えるメッセージ文字列を指定できます。  
  
> [!CAUTION]
>  配置した場合、 **Terminate**図形内、**並列アクション**図形とで、分岐、 **Terminate**では、実行、インスタンスが、すぐに完了に関係なくかどうか、他の分岐の実行が完了します。 デザイン方法によっては、この場合の結果が予測できないものになる可能性があります。  
  
> [!CAUTION]
>  場合、 **Terminate**図形が同期的に呼び出されたオーケストレーションで検出された (と同様、**呼び出す**図形) によって別のオーケストレーション、入れ子になったインスタンスおよびそれを囲むすべてのオーケストレーションインスタンスは終了されます。  
  
### <a name="to-configure-a-terminate-shape"></a>終了図形を構成するには  
  
-   使用することができます、**エラー メッセージ**プロパティ グループ ハブ ページのクエリ出力に表示する際に図形に関連付けるテキストを指定します。 このテキストはリテラル文字列、またはに評価される式が適用される場合があります、 **System.String**です。  
  
    > [!CAUTION]
    >  リテラル文字列を入力する場合は、二重引用符で囲む必要があります。