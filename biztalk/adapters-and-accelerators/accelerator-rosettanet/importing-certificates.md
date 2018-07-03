---
title: 証明書のインポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing certificates
- certificates, importing
ms.assetid: c2576f89-b5de-4250-9c54-74c8a218bb39
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96bdc2a681cf3632f6393a3fef05ec275f60f82f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006083"
---
# <a name="importing-certificates"></a>証明書のインポート
ここでは、インポート先、格納先、インポートに使用するツールなど、証明書のインポート方法について説明します。  
  
 証明書をインポートする方法は 2 つあります。 Microsoft 管理コンソール (MMC) を CertWizard ツールまたは証明書スナップインに使用することができます。  
  
- CertWizard は、スイッチの設定に基づいて証明書の使用法を構成する段階的なコマンド ライン ウィザードです。 このツールは、Microsoft で使用できる[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]SDK フォルダー。  
  
- MMC の証明書スナップインを使用しても、証明書を証明書ストアにインポートできます。 ただし、この手動プロセスを使用した場合は、証明書の使用法を個別に構成する必要があります。  
  
  > [!IMPORTANT]
  >  MMC のプライベート証明書をインポートまたは使用するには、ログオンしているユーザーが BizTalk ホストのユーザー ID を持っている必要があります。 そうでないを実行する必要がある場合、 **runas**コマンドと、ユーザー スイッチとホスト サービス アカウントは、証明書 MMC の起動を**runas/user:hostsvc mmc**します。 このコマンドを実行することにより、BizTalk ホスト (BizTalkServerApplication および BizTalkServerIsolatedHost) のユーザー ID を想定します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [証明書のインポート元と証明書ストア](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)  
  
-   [CertWizard ユーティリティを使用した証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)  
  
-   [MMC を使用した証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)