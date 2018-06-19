---
title: BizTalk Server 2013 および 2013 R2 へのアップグレード |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- upgrading, BizTalk Server
- deploying [BizTalk Server], upgrading
- BizTalk Server, upgrading
- upgrading
ms.assetid: acb0a96e-091b-45c3-8d41-affe9ffcf134
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97337438ca6be06b542baf61ad8d26fa2045180a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300034"
---
# <a name="upgrade-to-biztalk-server-2013-and-2013-r2"></a>BizTalk Server 2013 および 2013 R2 へのアップグレード
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、以前のバージョンから簡単にアップグレードできるように設計されています。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 および 2013 R2 のアップグレード ガイドは、「[BizTalk Server 2013 に関連するインストール ガイド](http://www.microsoft.com/download/details.aspx?id=35552)」でご覧いただけます。  
  
> [!NOTE]
>  アップグレードを実行すると、スキーマの圧縮ファイルが置き換えられます。 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を新しいビルドにアップグレードするとき (ベータ版からリテール リリース バージョンにアップグレードするときなど)、環境内の MicrosoftEdiXSDTemplates.exe ファイルが、アップグレードに関連付けられた MicrosoftEdiXSDTemplates.exe ファイルに置き換えられます。 古い圧縮ファイルのスキーマを引き続き使用する場合は、古い圧縮ファイルをバックアップしない限り、アップグレード後、圧縮ファイルにアクセスできなくなります。 詳細については、次を参照してください。**インストール EDI スキーマ**で[、環境を最適化するために後の構成手順](post-configuration-steps-to-optimize-your-environment.md)です。
  
## <a name="see-also"></a>参照  
[BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)