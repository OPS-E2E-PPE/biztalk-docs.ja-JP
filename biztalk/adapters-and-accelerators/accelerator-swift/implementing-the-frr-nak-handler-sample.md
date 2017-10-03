---
title: "FRR NAK ハンドラーのサンプルを実装する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80fa5fb7-6864-4923-b641-e76d2b95d923
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4233bf7f81cf7e645440e18a54479c8aa81094e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-the-frr-nak-handler-sample"></a>FRR NAK ハンドラーのサンプルを実装します。
サンプル FRR NAK カスタム ハンドラーを実装して、サンプル プロジェクトをソリューションに追加、ビルドし、プロジェクトを配置、バインドし、オーケストレーションを開始および停止し、再開する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
### <a name="to-implement-the-frr-nak-custom-handler"></a>FRR NAK カスタム ハンドラーを実装するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューションを開きます。 ソリューション エクスプ ローラーでソリューションを右クリックし、**追加**、クリックして**既存のプロジェクト**です。  
  
2.  **既存プロジェクトの追加** ダイアログ ボックスに移動*\<ドライブ >*: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Samples\FrrHandler です。 選択**RepairSWIFTRejectedMessage.btproj**、クリックして**開く**です。  
  
3.  キーを生成し、キーをプロジェクトに割り当てます。  
  
4.  ビルドして RepairSWIFTRejectedMessage.btproj プロジェクトを配置します。  
  
5.  BizTalk エクスプ ローラーで、 **BizTalk 構成データベース**、   **\<*サーバー名*>、BizTalkMgmtDb.dbo**、および**オーケストレーション**を右クリックして**RepairSWIFTRejectedMessage.Orchestration_1**、クリックして**バインド**です。  
  
6.  **ポート バインド プロパティ**ダイアログ ボックスでは、BizTalkServerApplication など、ホストを選択し、をクリックして**OK**です。  
  
7.  BizTalk エクスプ ローラーで右クリック**RepairSWIFTRejectedMessage.Orchestration_1**、クリックして**開始**です。  
  
8.  **スタート**ダイアログ ボックスで、をクリックして**OK**です。  
  
9. **[スタート]**ボタンをクリックし、 **[ファイル名を指定して実行]**をクリックします。 入力**services.msc**、順にクリック**OK**です。 右クリック**BizTalk サービス**、クリックして**再起動**です。