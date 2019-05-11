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
ms.openlocfilehash: 96dd45cb6a4f973b98a0a7a4a0c32c2d8452c0a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283653"
---
# <a name="importing-certificates"></a>証明書のインポート
このセクションは、証明書をインポートする方法を説明しますからそれらをインポートする場所、それを格納する場所を使用してそれらをインポートするどのようなツールなど。  
  
 証明書をインポートする 2 つの方法はあります。 Microsoft 管理コンソール (MMC) を CertWizard ツールまたは証明書スナップインに使用することができます。  
  
- CertWizard は、スイッチの設定に基づく証明書の使用を構成するステップ バイ ステップのコマンド ライン ウィザードです。 このツールは、Microsoft で使用できる[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]SDK フォルダー。  
  
- 証明書スナップイン MMC で、証明書ストアに証明書をインポートできます。 ただし、この手動プロセスでは、証明書の使用を個別に構成することが必要です。  
  
  > [!IMPORTANT]
  >  インポートまたは MMC のプライベート証明書の使用、ログオンしているユーザーは、BizTalk ホストのユーザー id が必要です。 そうでないを実行する必要がある場合、 **runas**コマンドと、ユーザー スイッチとホスト サービス アカウントは、証明書 MMC の起動を**runas/user:hostsvc mmc**します。 このコマンドを実行すると、BizTalk ホスト (BizTalkServerApplication および BizTalkServerIsolatedHost) のユーザー id を想定します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [証明書のインポート元と証明書ストア](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)  
  
-   [CertWizard ユーティリティを使用した証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)  
  
-   [MMC を使用した証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)