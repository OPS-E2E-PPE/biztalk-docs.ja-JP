---
title: 証明書のソースとストア |Microsoft ドキュメント
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
ms.openlocfilehash: f3ade897bb51850b4ef9dd6b530f5fc04c6b2601
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
ms.locfileid: "22210234"
---
# <a name="certificate-sources-and-stores"></a>証明書のソースおよびストア
ここでは、証明書のインポート元および証明書の格納先について説明します。  
  
## <a name="certificate-sources"></a>証明書のソース  
 各種証明書のインポート元は次のとおりです。  
  
-   プライベート証明書.pfx ファイルまたは .p12 ファイルからインポートします。 証明書をインポートしたら、これらのファイルを安全に格納します。 CertWizard ユーティリティを使用してプライベート証明書をインポートする場合は、設定、 **/exportable**に切り替える`False`、これが既定の設定、ファイルにストアからプライベート証明書をエクスポートできないようにします。 設定した場合、 **/exportable**に切り替える`True`、これらの証明書をファイルにエクスポートするには、証明書から[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]管理コンソール (MMC) です。  
  
-   パブリック証明書.cer ファイルまたは .der ファイルからインポートします。 パートナーは、これらのファイルを使用して証明書を送信します。  
  
-   ルート証明書.cer ファイルまたは .der ファイルからインポートします。 証明機関は、これらのファイルを使用してルート証明書を送信します。  
  
## <a name="certificate-storage"></a>証明書記憶域  
 証明書は、ローカル コンピューター上に 2 つある証明書ストアのいずれか 1 つにインポートします。 パブリック証明書を格納する、**証明書 (ローカル コンピューター)** を格納します。 このストアのノードを開くことによって開くことができます、**証明書 (ローカル コンピューター)** 内のノード、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) 管理コンソールです。 アクセスすることができます、**証明書 (ローカル コンピューター)** コンピューターで管理者権限がある場合は、保存します。 各種パブリック証明書の格納先は次のとおりです。  
  
-   ホーム パブリック証明書個人用フォルダーに、**証明書 (ローカル コンピューター)** 格納  
  
-   パートナー パブリック証明書の [その他の人] フォルダーで、**証明書 (ローカル コンピューター)** 格納  
  
-   信頼されたルート証明機関 フォルダーに証明機関から証明書、**証明書 (ローカル コンピューター)** 格納  
  
 プライベート証明書を格納する、**証明書 - 現在のユーザー**を格納します。 管理コンソールを使用して、開くことによって、このストアのノードを開くことができます、 **runas**コマンド ホスト サービス アカウントのユーザーにします。 詳細については、次を参照してください。[証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates.md)です。  
  
## <a name="see-also"></a>参照  
 [CertWizard ユーティリティを使用して証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-the-certwizard-utility.md)   
 [MMC を使用して証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/importing-certificates-using-mmc.md)   
 [証明書のインポート&#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/certificate-sources-and-stores.md)