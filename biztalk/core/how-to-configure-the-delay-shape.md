---
title: "遅延図形を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Delay shape [Orchestration Designer], configuring
- Delay shape [Orchestration Designer]
- Delay shape [Orchestration Designer], timeouts
- Delay shape [Orchestration Designer], about Delay shape
- configuring [Orchestration Designer], Delay shapes
ms.assetid: 727be28d-932a-41d5-af3f-3ee6f7129a17
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b76448398facd3af7f3b9712491f9895ffb406d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-delay-shape"></a>遅延図形を構成する方法
![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")  
遅延図形  
  
 タイムアウトを指定する 2 つの方法、**遅延**:  
  
-   使用することができます**System.DateTime**それが原因で、指定した日付までを一時停止するオーケストレーション、および日時に達した。  
  
     System.DateTime.UtcNow.AddSeconds(60)  
  
    > [!NOTE]
    >  遅延表現する必要が世界協定時刻 (UTC) で使用するときに**DateTime**です。  
  
-   使用することができます**System.TimeSpan**、それが原因で、オーケストレーションを時間の指定された長さの一時停止します。  
  
     System.TimeSpan(0, 1, 0)  
  
 場合、**遅延**図形内部にある、**リッスン**図形、する必要はありません、式の末尾にセミコロンを追加します。  
  
 詳細については**System.DateTime**と**System.TimeSpan**、"DateTime 構造体」および「TimeSpan 構造体」を参照して、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]連結ヘルプ コレクションです。  
  
> [!NOTE]
>  複数のコンピューターのインストール環境で、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Server が別々 のコンピューターにインストールされていると、**遅延**図形が時間のために予想よりも早く終了する可能性があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]マシンは同期されていません。  
  
> [!NOTE]
>  ストレス条件下で指定されたタイムアウト、**遅延**図形に指定したよりも後で発生する可能性があります。 この遅れは、ストレス条件下でスレッドが不足するために起こります。  
  
### <a name="to-configure-a-delay-shape"></a>遅延図形を構成するには  
  
1.  BizTalk 式エディターが表示されていない場合を右クリックし、**遅延**図形をクリックして**遅延の編集**、[プロパティ] ウィンドウで次のようにクリックしますまたは、**省略記号**( **。...**) ボタンをクリックして、**式**プロパティです。  
  
2.  BizTalk 式エディタで、作成を返す式、 **System.DateTime**オブジェクトまたは**System.TimeSpan**オブジェクト。 詳細については、次を参照してください。[式の要件と制限](../core/requirements-and-limitations-for-expressions.md)です。