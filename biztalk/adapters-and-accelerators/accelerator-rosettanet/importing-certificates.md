---
title: "証明書のインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing certificates
- certificates, importing
ms.assetid: c2576f89-b5de-4250-9c54-74c8a218bb39
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c78773d6eb1fc7e51ca80afadfd282d54def80b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="importing-certificates"></a>証明書のインポート
ここでは、インポート先、格納先、インポートに使用するツールなど、証明書のインポート方法について説明します。  
  
 証明書をインポートする方法は 2 つあります。 CertWizard ツールを使用する方法と、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] 管理コンソール (MMC) の証明書スナップインを使用する方法です。  
  
-   CertWizard は、スイッチの設定に基づいて証明書の使用法を構成する段階的なコマンド ライン ウィザードです。 このツールで使用できる、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK のフォルダーです。  
  
-   MMC の証明書スナップインを使用しても、証明書を証明書ストアにインポートできます。 ただし、この手動プロセスを使用した場合は、証明書の使用法を個別に構成する必要があります。  
  
    > [!IMPORTANT]
    >  MMC のプライベート証明書をインポートまたは使用するには、ログオンしているユーザーが BizTalk ホストのユーザー ID を持っている必要があります。 Not を実行する場合、 **runas**コマンド、ユーザー スイッチと証明書 MMC を起動するホスト サービス アカウントと**runas/user:hostsvc mmc**です。 このコマンドを実行することにより、BizTalk ホスト (BizTalkServerApplication および BizTalkServerIsolatedHost) のユーザー ID を想定します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [証明書のソースおよびストア](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)  
  
-   [CertWizard ユーティリティを使用して証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)  
  
-   [MMC を使用して証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)