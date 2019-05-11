---
title: 終了図形を構成する方法 |Microsoft Docs
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
ms.openlocfilehash: 177666efceb34d78b492c93b7f365fc36c3855bb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340291"
---
# <a name="how-to-configure-the-terminate-shape"></a>終了図形を構成する方法
![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")  
終了図形  
  
 終了図形を使用して、オーケストレーション インスタンスを終了します。 グループ ハブ ページからの出力で表示したときに図形に添えるメッセージ文字列を指定することができます。  
  
> [!CAUTION]
>  配置した場合、 **Terminate**図形内、**並列アクション**形状、および分岐を**Terminate**で実行されて、インスタンスが、すぐに完了に関係なくかどうか他の分岐の実行が完了します。 設計によって結果予測できないここでします。  
  
> [!CAUTION]
>  場合、 **Terminate**が同期的に呼び出されたオーケストレーションの図形が検出された (と同様、**呼び出す**図形) 別のオーケストレーション、入れ子になったインスタンスおよびそれを囲むすべてのオーケストレーションインスタンスは終了されます。  
  
### <a name="to-configure-a-terminate-shape"></a>終了図形を構成するには  
  
-   使用することができます、**エラー メッセージ**グループ ハブ ページでクエリの出力に表示したときに図形に関連付けるテキストを指定するプロパティ。 このテキスト リテラル文字列の場合、またはに評価される式が適用される場合があります、 **System.String**します。  
  
    > [!CAUTION]
    >  リテラル文字列を入力する場合は、引用符で囲む必要があります。