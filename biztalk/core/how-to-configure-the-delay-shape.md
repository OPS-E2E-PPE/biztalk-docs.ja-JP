---
title: 遅延図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Delay shape [Orchestration Designer], configuring
- Delay shape [Orchestration Designer]
- Delay shape [Orchestration Designer], timeouts
- Delay shape [Orchestration Designer], about Delay shape
- configuring [Orchestration Designer], Delay shapes
ms.assetid: 727be28d-932a-41d5-af3f-3ee6f7129a17
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdfe0ca86475f3d330faea1fa5cd084fa3af4910
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386125"
---
# <a name="how-to-configure-the-delay-shape"></a>遅延図形を構成する方法
![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")  
遅延図形  
  
 タイムアウトを指定する 2 つの方法がある、**遅延**:  
  
- 使用することができます**System.DateTime**を指定した日付まで一時停止するオーケストレーションを停止して、時間に到達します。  
  
   System.DateTime.UtcNow.AddSeconds(60)  
  
  > [!NOTE]
  >  使用する場合、遅延で世界協定時刻 (UTC) でが表現する必要があります**DateTime**します。  
  
- 使用することができます**System.TimeSpan**、指定した長さの時間一時停止するオーケストレーションを停止します。  
  
   System.TimeSpan(0, 1, 0)  
  
  場合、**遅延**内の図形は、**リッスン**図形、する必要はありません、式の末尾にセミコロンを追加します。  
  
  詳細については**System.DateTime**と**System.TimeSpan**の「DateTime 構造体」および「TimeSpan 構造体」を参照してください、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]連結ヘルプ コレクションです。  
  
> [!NOTE]
>  複数のマシンのインストール環境で、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Server が別々 のコンピューターにインストールされていると、**遅延**図形がで時間が原因で予期される値よりも早く終了する可能性があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]マシンは同期されません。  
> 
> [!NOTE]
>  ストレス条件下で、タイムアウトが指定された、**遅延**図形に指定したものよりも後で発生する可能性があります。 この遅れは、ストレス条件下でスレッドが不足するために起こります。  
  
### <a name="to-configure-a-delay-shape"></a>遅延図形を構成するには  
  
1.  BizTalk 式エディターが表示されていない場合を右クリックし、 **遅延** 図形を **遅延の編集**, は、[プロパティ] ウィンドウで、 **省略記号** (**...**) ボタンをクリックして、 **式** プロパティです。  
  
2.  BizTalk 式エディターで、作成を返す式、 **System.DateTime**オブジェクトまたは**System.TimeSpan**オブジェクト。 詳細については、次を参照してください。[式の要件と制限](../core/requirements-and-limitations-for-expressions.md)します。