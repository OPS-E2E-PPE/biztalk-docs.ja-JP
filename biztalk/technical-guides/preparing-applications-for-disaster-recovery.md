---
title: アプリケーションのディザスター リカバリーの準備 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0ef93099-aa6b-424a-a4ce-87d855c6afe3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b9d328d8c1e2f8085c8a1a1709a78824661f62c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379460"
---
# <a name="preparing-applications-for-disaster-recovery"></a>アプリケーションのディザスター リカバリーの準備
BizTalk アプリケーション (バイナリと構成アイテムなどの受信場所と送信ポート) は、ディザスター リカバリー サイトで、グループが復元されるときに、運用環境の BizTalk グループにデプロイされます。 この構成は、かどうかに応じて変更する必要がありますは受信場所と運用環境に固有のポートの送信などの構成の場所があります。  
  
 ディザスター リカバリー サイトでアプリケーションの復元を高速化、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でバイナリをインストールする .msi ファイル、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サーバーの実行時間保持する必要が最新の状態のディザスター リカバリー[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行時のサーバー。 ディザスター リカバリーに固有のアプリケーション構成の .msi ファイルをなど、アプリケーションの災害復旧に固有の成果物を構成するためにインストールする必要があります、ディザスター リカバリー サイトで運用環境の BizTalk グループが復元されると、受信場所と、必要に応じて、送信ポート。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開](../technical-guides/deploying-an-application.md)