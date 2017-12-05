---
title: "SAP アダプターの概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: adapters, overview
ms.assetid: 2d078b13-d41f-476f-bfb4-82be4d35a769
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3031bdf1317d96f64f1ea247c6f8cbf83e1688c7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="overview-of-the-sap-adapter"></a>SAP アダプターの概要
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]を WCF サービスとして SAP システムを公開します。 アダプターのクライアントは、アダプターと SOAP メッセージを交換することで、SAP システムで操作を実行できます。 アダプターは WCF メッセージを処理して、操作を実行する SAP システムへの適切な呼び出しを行います。 アダプターは、SOAP メッセージの形式でクライアントに SAP システムからの応答を返します。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WSDL の形でメッセージの SOAP の構造を記述する SAP アイテム (RFC、BAPI、IDOC) のサーフェス メタデータ。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を使用して[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]アダプター クライアント操作のメタデータを取得するには、プログラミング ソリューションで使用できるプログラミングの成果物を生成します。 詳細については[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]を参照してください[Visual Studio での SAP システムへの接続](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)です。  
  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Unicode RFC ライブラリ、librfc32u.dll を使用してサポートするその他の Dll を使うことに加えて、SAP システムと通信します。 アダプターを必要とする SAP Dll の完全な一覧を参照してください、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール ガイドです。 インストール ガイドがインストールされている通常\<インストール ドライブ:\>\Program Files\\[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents です。 使用することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次のように、SAP システムと通信します。  
  
-   BizTalk アプリケーションを開発することによりします。 参照してください[BizTalk Server アプリケーションの開発](../../core/developing-biztalk-server-applications.md)詳細についてはします。  
  
-   使用して、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]サービス モデル。 参照してください[WCF サービス モデルを使用して開発 SAP アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)です。
  
-   WCF チャネル モデルを使用します。 参照してください[WCF チャネル モデルを使用して開発 SAP アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)です。
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [アダプターは、SAP システムにどのように接続しますか。](https://msdn.microsoft.com/library/cc185540.aspx)  
  
-   [画面の SAP メタデータのアダプターがどのようにしますか。](https://msdn.microsoft.com/library/dd788039.aspx)  
  
-   [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/dd788159.aspx)  
  
-   [アダプターでサポートされているその他の機能](https://msdn.microsoft.com/library/dd788022.aspx)  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for mySAP Business Suite について](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)