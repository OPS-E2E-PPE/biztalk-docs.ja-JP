---
title: MQSeries アダプターのセキュリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, MQSeries adapters
- MQSeries adapters, security
ms.assetid: 0bd82c21-6b77-4a66-a4e9-4a91ba4a56c4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca3ef0bf698515d00b60e7ffb8b2124576e9a001
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019519"
---
# <a name="security-with-the-mqseries-adapter"></a>MQSeries アダプタでのセキュリティ

MQSeries アダプタをセキュリティで保護するには、BizTalk Server と MQSeries Server をセキュリティで保護する必要があります。 BizTalk Server をセキュリティで保護する方法の詳細については、[セキュリティで保護されたデータの保護と](secure-and-protect-your-biztalk-messages.md)を参照してください。 MQSeries Server をセキュリティで保護する方法の詳細については、IBM MQSeries Server のマニュアルを参照してください。  
  
> [!NOTE]
>  MQSeries アダプタでは、BizTalk Server と MQSeries Server 間のメッセージの送受信にパケット プライバシーが自動的に使用されます。  

## <a name="adapter-security"></a>アダプターのセキュリティ  
 アダプタ自体をセキュリティで保護した状態で使用するには、次の 4 つの事項に注意する必要があります。  
  
- MQSAgent 用のアプリケーション ID とメンバの選択  
  
- アダプタを使用した、BizTalk Server アカウントの管理  
  
- キュー作成スクリプトのセキュリティ保護  
  
- 適切な使用、 **SSO 関連アプリケーション**プロパティ  
  
  構成時にアプリケーション ID に割り当てられるアカウントは、管理者アカウント以外のアカウントにする必要があります。 代わりに、このアカウントは必要最小限の権限が必要-読み取りと MQSeries キューへの書き込みアクセス。  
  
  MQSAgent のロールには、アダプタを使用して BizTalk Server アカウントのみを割り当てるようにします。  
  
  キュー定義の処理中に作成されたスクリプトをエクスポートして使用する場合、スクリプトはセキュリティで保護された場所に格納するようにします。 また、管理者がスクリプトを使用した場合にのみアクセスできるようにする必要があります。  
  
  アプリケーションでは、送信メッセージにユーザーの資格情報を MQCIH および MQIIH ヘッダー プロパティを使用する場合は、使用、 **SSO 関連アプリケーション**プロパティを**トランスポートのプロパティ**ページ。 このプロパティの詳細については、[MQSeries アダプター受信場所の構成、送信ポートを](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターの構造](../core/structure-of-the-mqseries-adapter.md)   
 [MQSeries アダプターとは](../core/what-is-the-mqseries-adapter.md)