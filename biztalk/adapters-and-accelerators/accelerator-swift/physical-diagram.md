---
title: 物理的なダイアグラム |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, network configuration
ms.assetid: 4291727b-8687-496a-8f03-0da4b3201967
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fafd068c0fe55d65d47518dcd0693a0ba1f71e3a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377091"
---
# <a name="physical-diagram"></a>物理的なダイアグラム
一般的な展開には、メッセージング (送信および受信) の BizTalk Server コンピューターがクラスター化されたが、ビジネス プロセス (オーケストレーション)、InfoPath テンプレート (MRSR サイト) にアクセスするための BizTalk Server コンピューターを実行するための BizTalk Server コンピューターとクラスター化された SQL Server コンピューター。 次のような配置により、イントラネットとインターネット ユーザーの両方からセキュリティで保護された環境です。  
  
> [!NOTE]
>  この一般的な展開は、推奨される構成です。 独自のビジネス ニーズやサーバーの構成、デプロイが正常に動作していることを確認する必要があります。  
  
 この展開アップまたはスケール ダウン、または使用状況のプロファイルと成長を続けるビジネス ニーズに応じて、スケールできます。 スケーラビリティの一般的なシナリオにはより高い可用性やスループットを向上させることを確認するには、各クラスター内の 1 つまたは複数のサーバーの追加が含まれます。 小規模な企業が、同じサーバーでいずれかであるなど、複数の関数を実行して、デプロイをスケール バックを優先する可能性があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]コンピューターは、オーケストレーションとメッセージングの両方を処理します。 Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] 1 台のサーバーの展開をサポートしています。 次の図は、完全な A4SWIFT 展開用の推奨される分散型展開環境の例を示します。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-deploy-full.gif "FSA_Deploy_Full")  
A4SWIFT の完全なデプロイの例