---
title: BizTalk Server で RosettaNet Loopback チュートリアルの前提条件 |Microsoft Docs
description: BizTalk Server では、RosettaNet アクセラレータの (BTARN) Loopback チュートリアルの手順の前提条件
caps.latest.revision: 9
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e26696c-86c5-448b-9cd6-bfd4a279151a
ms.author: mandia
ms.openlocfilehash: 807aa4002f08c9cb9f40f2bc6dad216bc2d730a2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282626"
---
# <a name="prepare-for-the-tutorial"></a>チュートリアルを準備します。

## <a name="prerequisites"></a>前提条件
前に、Loopback のチュートリアルを開始するには。
  
-   [インストールし、構成](install-configure-biztalk-accelerator-for-rosettanet.md)アクセラレータ。 SharePoint サーバーの全体管理で Windows SharePoint の管理パスの除外一覧に btarnhttpreceive 仮想ディレクトリを追加する必要があります。  
  
-   必ず、BizTalkServerIsolatedHost ホストと BizTalkServerApplication ホスト、**認証が信頼済み**オプションを有効にします。 確認する、BizTalk Server 管理コンソールを開き、展開**ホスト**します。 ホストを右クリックして**プロパティ**、確認と**信頼されている認証**が有効になっていない場合。  

    1 つ以上のホスト インスタンスがある場合は、すべてが 1 つのホスト インスタンスを削除します。 たとえば、BizTalk Server 分離ホスト インスタンスを削除および、BizTalkServerApplication ホスト インスタンスを保持)。 これにより、選択した**信頼されている認証**に関連付けられているホスト インスタンス、およびその他のホスト インスタンスを再作成します。  
  
## <a name="next-step"></a>次の手順
 [ステップ 1: ホーム組織の作成](step-1-create-the-home-organization.md)