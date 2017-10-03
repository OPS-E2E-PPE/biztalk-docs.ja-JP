---
title: "BizTalk Server で RosettaNet のダブル アクション チュートリアルの前提条件 |Microsoft ドキュメント"
description: "BizTalk Server では、RosettaNet accelerator (BTARN)、ダブル アクション チュートリアルの手順の前提条件"
ms.custom: 
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ce8a122-cd16-450a-84bd-bb6beee7af40
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87e2750a16d2c65b5838b6d61f27cbd2b2ff9885
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="prepare-for-the-double-action-tutorial"></a>ダブル アクション チュートリアルを準備します。

## <a name="prerequisites"></a>前提条件
このチュートリアルを開始: する前に
  
-   BizTalk Server の完全インストールを行うと[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]2 台のコンピューター。 詳細については、次を参照してください。[をインストールして構成する](install-configure-biztalk-accelerator-for-rosettanet.md)です。  
  
    > [!IMPORTANT]
    >  BTARN オーケストレーションを開始するなど、RosettaNet accelerator を完全に構成することを確認します。 参照してください[をインストールして構成する](install-configure-biztalk-accelerator-for-rosettanet.md)です。
  
-   このチュートリアルでは、ループバック アグリーメントを持つ 1 台のコンピューターではなく 2 台のコンピューターを使用して、実際のシナリオをシミュレートします。 このチュートリアルで使用するコンピューター名は、プレースホルダーとして示されます。 選択した実際のコンピューター名でそのプレース ホルダーを置き換えます。 たとえば、コンピューター、Contoso ソリューションを実行している場合は、という名前の**Contoso**のチュートリアルでは置換\\ \\< contoso**_** *コンピューター*> そのコンピューターの名前を持つ。  
  
-   このチュートリアルでは、Contoso と Fabrikam の間で証明書を使用する、セキュリティで保護された通信の使用を推奨します。 を必要として、それぞれのコンピューターでインストールするには、すべての証明書を生成する必要があります。  
  
## <a name="next-steps"></a>次の手順 
  
-   [手順 1: 証明機関の作成](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-a-certification-authority.md)  
  
-   [手順 2: パブリックおよびプライベート証明書の作成](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)  
  
-   [手順 3: パブリックおよびプライベート証明書のインポート](../../adapters-and-accelerators/accelerator-rosettanet/step-3-importing-public-and-private-certificates.md)  
  
-   [手順 4: IIS でレイヤーをソケット セキュリティで保護を有効にします。](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)