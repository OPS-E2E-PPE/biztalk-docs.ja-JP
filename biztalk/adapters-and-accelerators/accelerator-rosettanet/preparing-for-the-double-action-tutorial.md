---
title: BizTalk Server で RosettaNet のダブル アクション チュートリアルの前提条件 |Microsoft Docs
description: BizTalk Server では、RosettaNet アクセラレータ (BTARN) のダブル アクション チュートリアルの手順の前提条件
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ce8a122-cd16-450a-84bd-bb6beee7af40
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48584cf7dfee0ca4812b41e56b4e8f7c0984e4fc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979011"
---
# <a name="prepare-for-the-double-action-tutorial"></a>ダブル アクション チュートリアルを準備します。

## <a name="prerequisites"></a>前提条件
前に、チュートリアルを開始するには。
  
- BizTalk Server のフル インストールを行うと[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]2 台のコンピューター。 詳細については、次を参照してください。[インストールおよび構成](install-configure-biztalk-accelerator-for-rosettanet.md)します。  
  
  > [!IMPORTANT]
  >  BTARN オーケストレーションを開始するなど、RosettaNet アクセラレータを完全に構成してください。 参照してください[インストールおよび構成](install-configure-biztalk-accelerator-for-rosettanet.md)します。
  
- このチュートリアルでは、2 台のコンピューターを使用して、ループバック アグリーメントを持つ 1 台のコンピューターではなく、実際のシナリオをシミュレートします。 このチュートリアルで使用するコンピューター名は、プレースホルダーとして示されます。 選択した実際のコンピューター名では、そのプレース ホルダーを置き換えます。 たとえば、コンピューター、Contoso ソリューションを実行している場合がという名前**Contoso**のチュートリアルでは置換\\ \\< contoso<strong>_</strong> *コンピューター* \>そのコンピューターの名前。  
  
- このチュートリアルでは、Contoso と Fabrikam の間で証明書を使用する、セキュリティで保護された通信の使用を推奨します。 それぞれのコンピューターにインストールして、必要なすべての証明書を生成する必要があります。  
  
## <a name="next-steps"></a>次のステップ 
  
-   [手順 1: 証明機関の作成](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md)  
  
-   [手順 2: パブリック証明書とプライベート証明書の作成](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)  
  
-   [手順 3: パブリック証明書とプライベート証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)  
  
-   [手順 4: IIS で Secure Sockets Layer の有効化](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)