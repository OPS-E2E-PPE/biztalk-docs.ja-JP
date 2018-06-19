---
title: BizTalk Server で RosettaNet ループバック チュートリアルの前提条件 |Microsoft ドキュメント
description: BizTalk Server では、RosettaNet accelerator (BTARN) ループバック チュートリアルの手順の前提条件
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
ms.openlocfilehash: 9767f7823e80d4de67345ba0fbf59c1435adb8e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206962"
---
# <a name="prepare-for-the-tutorial"></a>チュートリアルを準備します。

## <a name="prerequisites"></a>前提条件
ループバック チュートリアルを開始する前に
  
-   [インストールし、構成](install-configure-biztalk-accelerator-for-rosettanet.md)アクセラレータです。 SharePoint サーバーの全体管理で Windows SharePoint の管理パスの除外一覧に btarnhttpreceive 仮想ディレクトリを追加する必要があります。  
  
-   必ず、BizTalkServerIsolatedHost ホストと BizTalkServerApplication ホスト、**認証が信頼済み**オプションを有効にします。 確認し、BizTalk Server 管理コンソールを開き、展開**ホスト**です。 ホストを右クリックし、選択**プロパティ**、し確認**信頼されている認証**が有効になっていない場合。  

    1 つ以上のホスト インスタンスがある場合は、1 つを除くすべてのホスト インスタンスを削除します。 たとえば、BizTalk Server 分離ホスト インスタンスを削除と、BizTalkServerApplication ホスト インスタンス)。 これにより、選択した**信頼されている認証**に関連付けられているホストのインスタンス、およびその他のホスト インスタンスを再作成します。  
  
## <a name="next-step"></a>次の手順
 [手順 1: ホーム組織を作成します。](step-1-create-the-home-organization.md)