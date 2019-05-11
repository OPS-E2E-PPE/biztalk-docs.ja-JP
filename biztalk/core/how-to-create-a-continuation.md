---
title: Continuation を作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities, relating events
- tracking profiles, relating events
- continuations, tracking profiles
- activities, continuations
- events, relating
- orchestrations, business events
- tracking profiles, updating
- activities, tracking profiles
- tracking profiles, continuations
- tracking profiles, connecting activities
ms.assetid: 31d6fc24-676e-418c-8e78-1a46b045905d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0cf558ec136cf25bece9c899cad13e1c9d75f1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340100"
---
# <a name="how-to-create-a-continuation"></a>Continuation を作成する方法
接続されたアクティビティを構築することによって関連する 1 つまたは複数のオーケストレーションでビジネス イベントを示すために、継続を作成します。  
  
> [!IMPORTANT]
>  追跡プロファイルを更新する場合に、アクティビティに BAM の Continuation が含まれていると、実行中のアクティビティ インスタンスに影響することがあります。 具体的には、追跡プロファイルの更新によって、既に記録されているアクティビティ項目に対してデータの下流傍受が指定されると、元の値が上書きされる可能性があります。 各ストリーム オブジェクトは、アクティビティまたはストリームが開始された時点で配置されたプロファイルの特定のバージョンに関連付けられているため、すべての単一のイベント ストリームは、実質的には追跡プロファイルの更新対象のアプリケーションによる影響を受けません。  ただし、Continuation は複数のイベント ストリームを関連付ける手段なので、プロファイルの更新の時点でまだ開始されていなかったストリームは、更新中に変更内容を取得します。その結果、上記のようなデータの上書きが発生する可能性があります。  
  
> [!NOTE]
>  メッセージを処理しないオーケストレーションでは、continuation を作成できます。 BAM Api を使用して、処理を継続してオーケストレーション間の実行呼び出しでパラメーターを渡すことによってメッセージの処理はオーケストレーションを同じ機能を取得できます。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行するには、必要がありますが展開した BAM アクティビティ定義とオーケストレーションに接続します。  
  
### <a name="to-create-a-continuation"></a>Continuation を作成するには  
  
1.  既存の追跡プロファイルを開くか、追跡プロファイルを作成します。 追跡プロファイルを作成する方法の詳細については、次を参照してください。[追跡プロファイルを作成する方法](../core/how-to-create-a-tracking-profile.md)します。  
  
2.  識別、*継続トークン、* 両方のアクティビティに使用できる一意の情報の一部であります。 たとえば場合、 **CreditHistory**アクティビティがから送信されたメッセージによってアクティブ化、 **LoanProcess**内のアクティビティ、 **EquityLoan**オーケストレーションの SSN フィールド、メッセージは、両方の活動に共通するために継続トークンとして使用できます。  
  
3.  アクティビティを右クリックし、**新しい Continuation** continuation (CreditHistory) を作成します。 作成した continuation のノードの名前を付けます。  
  
4.  オーケストレーション スケジュール ビューからは、SSN (ここでは送信アクション) などの手順 2. で選択した継続トークンを選択し、手順 3 で作成した continuation のノードにドロップします。  
  
5.  アクティビティを右クリックして**新しい ContinuationID** Continuation ID ノードを作成します。 手順 3. で指定した名前を使用して名前し、(この例では、受信アクションの SSN) では、対応するデータ項目を含むノードにドロップします。  
  
6.  **ファイル** メニューのをクリックして**名前を付けて保存**追跡プロファイルを BizTalk 管理データベースに .btt ファイルとして保存して、既存の .btt ファイルが上書きされないようにします。  
  
## <a name="see-also"></a>参照  
 [Continuation ノードと ContinuationID ノード](../core/continuation-and-continuationid-nodes.md)   
 [追跡プロファイルの作成](../core/creating-tracking-profiles.md)