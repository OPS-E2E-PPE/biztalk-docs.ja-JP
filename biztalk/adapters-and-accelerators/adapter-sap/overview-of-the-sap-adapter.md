---
title: SAP アダプターの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, overview
ms.assetid: 2d078b13-d41f-476f-bfb4-82be4d35a769
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58f6249774697e12e12ab5b85bccf6df210a5d4e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981843"
---
# <a name="overview-of-the-sap-adapter"></a>SAP アダプターの概要
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] WCF サービスとしての SAP システムを公開します。 アダプター クライアントは、アダプターを使用した SOAP メッセージを交換することで、SAP システムの操作を実行できます。 アダプターは WCF メッセージを使用し、操作を実行する SAP システムに適切な呼び出しを行います。 アダプターは、SOAP メッセージの形式でクライアントに SAP システムからの応答を返します。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WSDL の形式でメッセージの SOAP の構造を記述する SAP アイテム (RFC、BAPI、IDOC) の表面のメタデータ。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]アダプター クライアントの操作のメタデータを取得するには、プログラミング ソリューションで使用できるプログラミングの成果物を生成します。 詳細については[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]を参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)します。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Unicode RFC ライブラリを librfc32u.dll を他のサポートの Dll を使用するだけでなく、SAP システムとの通信に使用します。 アダプターを必要とする SAP Dll の完全な一覧を参照してください、 [BizTalk Adapter Pack のインストール ガイド](../../adapters-and-accelerators/biztalk-adapter-pack.md#install-bap)します。 使用することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次の方法で、SAP システムと通信します。  
  
- BizTalk アプリケーションを開発しています。 参照してください[BizTalk Server アプリケーションの開発](../../core/developing-biztalk-server-applications.md)詳細についてはします。  
  
- 使用して、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデル。 参照してください[WCF サービス モデルを使用して開発の SAP アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)します。
  
- WCF チャネル モデルを使用します。 参照してください[WCF チャネル モデルを使用して開発の SAP アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)します。
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [アダプターは、SAP システムにどのように接続でしょうか。](https://msdn.microsoft.com/library/cc185540.aspx)  
  
-   [アダプター メタデータのサーフェスの SAP のしくみですか。](https://msdn.microsoft.com/library/dd788039.aspx)  
  
-   [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/dd788159.aspx)  
  
-   [アダプターでサポートされているその他の機能](https://msdn.microsoft.com/library/dd788022.aspx)  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for mySAP Business Suite について](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)