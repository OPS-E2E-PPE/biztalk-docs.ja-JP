---
title: FRR NAK ハンドラー サンプルの実装 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80fa5fb7-6864-4923-b641-e76d2b95d923
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42885d6c487c6f088bfab113891ec5425d3fc82e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990283"
---
# <a name="implementing-the-frr-nak-handler-sample"></a>FRR NAK ハンドラー サンプルの実装
サンプル FRR NAK のカスタム ハンドラーを実装する、サンプル プロジェクトをソリューションに追加、ビルドしプロジェクトを展開、バインドし、オーケストレーションを開始および停止し、再開する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  

### <a name="to-implement-the-frr-nak-custom-handler"></a>FRR NAK のカスタム ハンドラーを実装するには  

1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューションを開きます。 ソリューション エクスプ ローラーでソリューションを右クリックして**追加**、 をクリックし、**既存のプロジェクト**します。  

2. **既存プロジェクトの追加** ダイアログ ボックスに移動*\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Samples\FrrHandler します。 選択**RepairSWIFTRejectedMessage.btproj**、 をクリックし、**オープン**します。  

3. キーを生成し、プロジェクトにキーを割り当てます。  

4. ビルドおよび RepairSWIFTRejectedMessage.btproj プロジェクトを配置します。  

5. BizTalk エクスプ ローラーで、 **BizTalk 構成データベース**、  **\<*サーバー名*\>、>.biztalkmgmtdb.dbo**、および**オーケストレーション**、右クリック**RepairSWIFTRejectedMessage.Orchestration_1**、 をクリックし、**バインド**します。  

6. **ポートのバインドのプロパティ**ダイアログ ボックスは、BizTalkServerApplication など、ホストを選択し、クリックして**OK**します。  

7. BizTalk エクスプ ローラーで右クリックして**RepairSWIFTRejectedMessage.Orchestration_1**、 をクリックし、**開始**します。  

8. **スタート**ダイアログ ボックスで、をクリックして**OK**。  

9. **[スタート]** ボタンをクリックし、 **[ファイル名を指定して実行]** をクリックします。 入力**services.msc**、 をクリックし、 **OK**。 右クリック**BizTalk サービス**、 をクリックし、**再起動**します。
