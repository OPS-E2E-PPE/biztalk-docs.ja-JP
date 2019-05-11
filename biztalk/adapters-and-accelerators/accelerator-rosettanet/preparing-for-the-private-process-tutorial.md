---
title: BizTalk Server で RosettaNet プライベート プロセス チュートリアルの前提条件 |Microsoft Docs
description: BizTalk Server では、RosettaNet アクセラレータ (BTARN) のプライベート プロセス チュートリアルの手順の前提条件
caps.latest.revision: 7
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89631ce3-f5af-4d30-b22f-6d20f595295f
ms.author: mandia
ms.openlocfilehash: 4f2a218063bc7f8d90205480887c90c6f6be78d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282723"
---
# <a name="prepare-for-the-private-process-tutorial"></a>プライベート プロセス チュートリアルを準備します。

## <a name="prerequisites"></a>前提条件
前に、チュートリアルを開始するには。
  
- BizTalk Server のフル インストールを行うと[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]2 台のコンピューター。 詳細については、次を参照してください。[インストールおよび構成](install-configure-biztalk-accelerator-for-rosettanet.md)します。  
  
  > [!IMPORTANT]
  >  BTARN オーケストレーションを開始するなど、RosettaNet アクセラレータを完全に構成してください。 参照してください[インストールおよび構成](install-configure-biztalk-accelerator-for-rosettanet.md)します。 追加する必要がありますも、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Microsoft Windows® SharePoint™ Services 管理パスの除外一覧に仮想ディレクトリ (btarnhttpreceive を含む)。 
  
- このチュートリアルでは、ループバック アグリーメントを使用して 1 台のコンピューターでシミュレートするのではなく、コンピューターを 2 台使用して、現実的なシナリオをシミュレートします。 このチュートリアルでは、コンピューター名を使用するたびに、コンピューター名としてプレース ホルダーを使用します。 選択した実際のコンピューター名では、そのプレース ホルダーを置き換えます。 たとえば、コンピューター、Contoso ソリューションを実行している場合がという名前**Contoso**のチュートリアルでは置換\\ \\< contoso<strong>_</strong> *コンピューター* \>そのコンピューターの名前。  
  
  このチュートリアルでは、Contoso と Fabrikam の間で証明書を使用する、セキュリティで保護された通信の使用を推奨します。 それぞれのコンピューターにインストールして、必要なすべての証明書を生成する必要があります。  
  
## <a name="next-steps"></a>次のステップ
  
-   [Contoso データベースの復元](../../adapters-and-accelerators/accelerator-rosettanet/restoring-the-contoso-database.md)  
  
-   [証明書の生成と有効化](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)