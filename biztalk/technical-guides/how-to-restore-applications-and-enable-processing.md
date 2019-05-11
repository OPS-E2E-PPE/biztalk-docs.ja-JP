---
title: アプリケーションを復元し、処理を有効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83144965-a51a-481a-afd6-7f573b69badb
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4c73d3ac6d96b1cfae4a8e8092669b6b0edcad0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400297"
---
# <a name="how-to-restore-applications-and-enable-processing"></a>アプリケーションを復元し、処理を有効にする方法
BizTalk グループで、アプリケーションを構成し、次のトピックで説明する手順の後にアプリケーションの処理を有効にする[ランタイム コンピューターの更新方法](../technical-guides/how-to-update-the-runtime-computers.md)します。  
  
### <a name="to-enable-application-configuration-and-restore-application-processing"></a>アプリケーションの構成を有効にして、アプリケーションの処理を復元するには  
  
1. 実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ内の各 BizTalk サーバー上のアプリケーションのインストールの MSI ファイルです。  
  
2. 実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ディザスター リカバリー サイトのアプリケーションを構成するには、グループの 1 つのサーバー上のアプリケーション構成の MSI ファイルです。 名前は、受信場所と送信ポートは変わりません。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をこれらの成果物が、ディザスター リカバリー環境で適切な場所を指すように、アプリケーション構成の MSI ファイルがバインドを更新します。  
  
   > [!NOTE]  
   >  場合は受信場所と送信ポートには影響しません、実稼働サイトの損失、いない必要がありますディザスター リカバリ固有の場所を使用してアプリケーションを再構成します。  
  
3. すべてのアプリケーションを有効にすると復元にアプリケーションの処理では、受信場所、ポート、およびホスト インスタンスを送信します。  
  
## <a name="see-also"></a>参照  
 [ランタイム コンピューターの回復](../technical-guides/recovering-the-runtime-computers.md)