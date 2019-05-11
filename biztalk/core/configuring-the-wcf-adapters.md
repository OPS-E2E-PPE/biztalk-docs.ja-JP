---
title: WCF アダプタの構成 |Microsoft Docs
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
ms.openlocfilehash: d3dbe2541a85879f21d6d2393280933d8335dac0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355129"
---
# <a name="configuring-the-wcf-adapters"></a>WCF アダプタの構成
BizTalk アダプターの Windows Communication Foundation (WCF) を許可する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]WCF ベースのアプリケーションと通信します。 BizTalk WCF アダプタには、WCF 定義済みバインドを表す 5 つの物理アダプタが含まれています —**BasicHttpBinding**、 **WsHttpBinding**、 **NetTcpBinding**、 **NetNamedPipeBinding**、および**NetMsmqBinding**します。 定義済みバインド用 WCF アダプタは、ほとんどのアプリケーション要件に必要な情報を簡単に構成するために提供されます。  
  
 BizTalk WCF アダプターでは、WCF バインドと動作については、受信場所の構成し、送信ポートを自由にするための 2 つのアダプターも含まれます。  
  
 すべてのプロパティ ダイアログ ボックスのようなトランスポートを提供する WCF アダプタは送信ポートと受信場所。 ただし、WCF アダプタを構成する詳細なタスクは、物理アダプターによって異なります。 証明書のインストールなど、アダプターのバインドに直接関連しないタスクは、すべての WCF アダプターは同じです。 このセクションでは、すべての WCF アダプタに共通するタスクについて説明します。 アダプターごとに異なるタスクについては、アダプターでの該当するトピックを参照してください。 [WCF アダプタ](../core/wcf-adapters.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [WCF アダプター プロパティ スキーマおよびプロパティ](../core/wcf-adapters-property-schema-and-properties.md)  
  
-   [WCF アダプターのセキュリティに関する推奨事項](../core/wcf-adapters-security-recommendations.md)  
  
-   [WCF アダプターの証明書のインストール](../core/installing-certificates-for-the-wcf-adapters.md)  
  
-   [WCF アダプターのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [WCF アダプターで WCF 機能拡張ポイントを有効にする方法](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)  
  
-   [WCF アダプターのパフォーマンス カウンタ](../core/wcf-adapters-performance-counters.md)  
  
-   [WCF アダプターのシングル サインオンのサポート](../core/single-sign-on-support-for-the-wcf-adapters.md)  
  
## <a name="see-also"></a>参照  
 [WCF アダプター](../core/wcf-adapters.md)