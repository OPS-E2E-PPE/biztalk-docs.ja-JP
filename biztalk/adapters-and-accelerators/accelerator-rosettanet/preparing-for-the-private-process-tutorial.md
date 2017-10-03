---
title: "BizTalk Server で RosettaNet プライベート プロセス チュートリアルの前提条件 |Microsoft ドキュメント"
description: "BizTalk Server では、RosettaNet accelerator (BTARN) のプライベート プロセス チュートリアルの手順の前提条件"
caps.latest.revision: "7"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89631ce3-f5af-4d30-b22f-6d20f595295f
ms.author: mandia
ms.openlocfilehash: 4da7190c7212f74a90689ca403d899eb1a849cc5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="prepare-for-the-private-process-tutorial"></a>プライベート プロセス チュートリアルを準備します。

## <a name="prerequisites"></a>前提条件
このチュートリアルを開始: する前に
  
-   BizTalk Server の完全インストールを行うと[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]2 台のコンピューター。 詳細については、次を参照してください。[をインストールして構成する](install-configure-biztalk-accelerator-for-rosettanet.md)です。  
  
    > [!IMPORTANT]
    >  BTARN オーケストレーションを開始するなど、RosettaNet accelerator を完全に構成することを確認します。 参照してください[をインストールして構成する](install-configure-biztalk-accelerator-for-rosettanet.md)です。 追加する必要がありますも、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Microsoft Windows® SharePoint™ Services 管理パスの除外一覧に仮想ディレクトリ (btarnhttpreceive を含む)。 
  
-   このチュートリアルでは、ループバック アグリーメントを使用して 1 台のコンピューターでシミュレートするのではなく、コンピューターを 2 台使用して、現実的なシナリオをシミュレートします。 このチュートリアルでは、コンピューター名を使用するたびに、コンピューター名としてプレース ホルダーを使用します。 選択した実際のコンピューター名でそのプレース ホルダーを置き換えます。 たとえば、コンピューター、Contoso ソリューションを実行している場合は、という名前の**Contoso**のチュートリアルでは置換\\ \\< contoso**_** *コンピューター*> そのコンピューターの名前を持つ。  
  
 このチュートリアルでは、Contoso と Fabrikam の間で証明書を使用する、セキュリティで保護された通信の使用を推奨します。 を必要として、それぞれのコンピューターでインストールするには、すべての証明書を生成する必要があります。  
  
## <a name="next-steps"></a>次の手順
  
-   [Contoso データベースの復元](../../adapters-and-accelerators/accelerator-rosettanet/restoring-the-contoso-database.md)  
  
-   [生成して、証明書の有効化](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)