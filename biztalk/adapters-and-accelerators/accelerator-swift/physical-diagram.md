---
title: 物理図 |Microsoft ドキュメント
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
ms.openlocfilehash: 0fcd0558d8fe3d45063a53800b1f3c082a2ba056
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22213962"
---
# <a name="physical-diagram"></a>物理的なダイアグラム
一般的な展開には、メッセージング (送信および受信) を BizTalk Server コンピューターがクラスター化されたビジネス プロセス (オーケストレーション)、InfoPath テンプレート (MRSR サイト) にアクセスするための BizTalk Server コンピューターを実行するための BizTalk Server コンピューターとクラスター化された SQL Server コンピューター。 次の展開では、イントラネットとインターネット ユーザーの両方からセキュリティで保護された環境が保証されます。  
  
> [!NOTE]
>  この一般的な展開は、推奨される構成です。 独自のビジネス ニーズとサーバーの構成、展開が正常に動作を確認することを確認する必要があります。  
  
 この展開を上下、out、または利用状況のプロファイルと増大するビジネス ニーズに応じてを拡張することができます。 一般的なスケーラビリティ シナリオには、高い可用性やスループットを向上させることを確認するには、各クラスター内の 1 つまたは複数のサーバーの追加が含まれます。 小規模な企業を使用しても、同じサーバーを 1 つを持つなど、複数の機能を実行して、展開でスケール バック[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]コンピューターは、オーケストレーションとメッセージングの両方を処理します。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]単一のサーバーに展開をサポートします。 次の図は、完全な A4SWIFT 展開に推奨される分散デプロイ環境の例を示します。  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-deploy-full.gif "FSA_Deploy_Full")  
A4SWIFT の完全展開の例