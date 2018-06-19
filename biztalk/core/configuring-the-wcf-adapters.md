---
title: WCF アダプタの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- NetTcpBinding [WCF adapters]
- configuring [WCF adapters]
- WCF adapters, pre-defined bindings
- configuring [WCF adapters], about configuring WCF adapters
- WsHttpBinding [WCF adapters]
- BasicHttpBinding [WCF adapters]
- NetNamedPipeBinding [WCF adapters]
- NetMsmqBinding [WCF adapters]
- bindings, pre-defined [WCF adapters]
- WCF adapters, configuring
ms.assetid: af01e2d4-303d-407a-b853-dd90b0246a8a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dde69bb5b2014a20509778e27230840e47c0b36d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233162"
---
# <a name="configuring-the-wcf-adapters"></a>WCF アダプタの構成
Windows Communication Foundation (WCF) 向け BizTalk アダプターを使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で WCF ベースのアプリケーションと通信できます。 BizTalk WCF アダプターは、WCF 定義済みバインドを表す 5 つの物理アダプターを含める-**BasicHttpBinding**、 **WsHttpBinding**、 **NetTcpBinding**、 **NetNamedPipeBinding**、および**NetMsmqBinding**です。 定義済みバインド用 WCF アダプタの目的は、大半のアプリケーション要件に必要な情報の構成を合理化することです。  
  
 BizTalk WCF アダプタには、受信場所と送信ポートに関する WCF バインドと動作情報を自由に構成するために使用される、2 つのアダプタも含まれています。  
  
 どの WCF アダプタの場合も、送信ポートと受信場所に関するトランスポート プロパティ ダイアログ ボックスは類似しています。 ただし、WCF アダプタを構成するための詳細なタスクは、物理アダプタごとに異なります。 アダプタ バインドと直接関連していないタスク (証明書のインストールなど) は、すべての WCF アダプタで同じです。 このセクションでは、すべての WCF アダプタに共通のタスクについて説明します。 アダプターごとに異なるタスクについては、アダプタの適切なトピックを参照して[WCF アダプタ](../core/wcf-adapters.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)  
  
-   [WCF アダプターのセキュリティに関する推奨事項](../core/wcf-adapters-security-recommendations.md)  
  
-   [WCF アダプターの証明書のインストール](../core/installing-certificates-for-the-wcf-adapters.md)  
  
-   [WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [WCF アダプターで WCF 機能拡張ポイントを有効にする方法](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)  
  
-   [WCF アダプターのパフォーマンス カウンター](../core/wcf-adapters-performance-counters.md)  
  
-   [WCF アダプタのシングル サインオンのサポート](../core/single-sign-on-support-for-the-wcf-adapters.md)  
  
## <a name="see-also"></a>参照  
 [WCF アダプタ](../core/wcf-adapters.md)