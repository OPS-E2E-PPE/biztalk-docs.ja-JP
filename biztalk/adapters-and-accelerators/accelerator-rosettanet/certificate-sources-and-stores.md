---
title: 証明書のソースとストア |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, certificate storage
- importing certificates
- certificates, certificate sources
- certificates, importing
ms.assetid: 3e98fb56-4368-46f3-9329-c44fed11f4fb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d099afcc6cecf229771e20551470027bf6bfe65
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284773"
---
# <a name="certificate-sources-and-stores"></a>証明書のソースおよびストア
ここでは、証明書のインポート元および証明書の格納先について説明します。  
  
## <a name="certificate-sources"></a>証明書のソース  
 各種証明書のインポート元は次のとおりです。  
  
- プライベート証明書.pfx ファイルまたは .p12 ファイルからインポートします。 証明書をインポートしたら、これらのファイルを安全に格納します。 CertWizard ユーティリティを使用してプライベート証明書をインポートする場合は設定できます、 **/exportable**に切り替える`False`、これは、既定の設定できるように、プライベート証明書がストアからファイルにエクスポートすることはできません。 設定した場合、 **/exportable**に切り替える`True`、するこれらの証明書ファイルにエクスポートできる、証明書 Microsoft 管理コンソール (MMC) から。  
  
- パブリック証明書.cer ファイルまたは .der ファイルからインポートします。 パートナーは、これらのファイルを使用して証明書を送信します。  
  
- ルート証明書.cer ファイルまたは .der ファイルからインポートします。 証明機関は、これらのファイルを使用してルート証明書を送信します。  
  
## <a name="certificate-storage"></a>証明書ストレージ  
 証明書は、ローカル コンピューター上に 2 つある証明書ストアのいずれか 1 つにインポートします。 パブリック証明書を格納する、**証明書 (ローカル コンピューター)** を格納します。 開き、このストアのノードを開くことができます、**証明書 (ローカル コンピューター)** ノードで、Microsoft [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) 管理コンソール。 アクセスできる、**証明書 (ローカル コンピューター)** コンピューターの管理アクセス許可がある場合に格納します。 各種パブリック証明書の格納先は次のとおりです。  
  
- ホーム パブリック証明書個人用フォルダーに、**証明書 (ローカル コンピューター)** 格納  
  
- パートナー パブリック証明書の他のユーザー フォルダー、**証明書 (ローカル コンピューター)** 格納  
  
- 信頼されたルート証明機関フォルダーに証明機関から証明書、**証明書 (ローカル コンピューター)** 格納  
  
  プライベート証明書を格納する、**証明書 - 現在のユーザー**を格納します。 管理コンソールを使用して、開くことで、このストアのノードを開くことができます、 **runas**コマンド ホスト サービス アカウントのユーザーにします。 詳細については、次を参照してください。[証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates.md)します。  
  
## <a name="see-also"></a>参照  
 [CertWizard ユーティリティを使用して証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)   
 [MMC を使用して証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)   
 [証明書のインポート&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)