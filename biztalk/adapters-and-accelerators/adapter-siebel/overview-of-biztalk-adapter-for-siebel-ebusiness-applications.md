---
title: BizTalk adapter 用 Siebel eBusiness Applications の概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- overview, adapter
- adapter, overview of
- adapter, overview
ms.assetid: 41ab7d42-7096-45ef-9763-a5ccf88eb652
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efcc3a90f7025a5f396cd778676f5f3152bc7657
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222042"
---
# <a name="overview-of-biztalk-adapter-for-siebel-ebusiness-applications"></a>BizTalk adapter 用 Siebel eBusiness Applications の概要
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]を WCF サービスとしての Siebel システムを公開します。 アダプターのクライアントは、アダプターと SOAP メッセージを交換することで Siebel システムの操作を実行できます。 アダプターは WCF メッセージを処理して、操作を実行する Siebel システムへの適切な呼び出しを行います。 アダプターは、SOAP メッセージの形式でクライアントに返送 Siebel システムの応答を返します。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] WSDL の形でメッセージの SOAP の構造を記述する Siebel の成果物 (ビジネス コンポーネント、ビジネス サービス) のサーフェス メタデータ。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]と[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]アダプター クライアント操作のメタデータを取得するには、プログラミング ソリューションで使用できるプログラミングの成果物を生成します。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システムにアクセスする Siebel COM データ コントロールを使用します。 Siebel COM データ コントロールは、Siebel Web クライアントに付属します。 そのためと同じコンピューターにインストールされている Siebel Web クライアントをしていることを確認、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 使用することができます、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]次の方法で Siebel システムと通信します。  
  
-   BizTalk アプリケーションを開発することによりします。 参照してください[BizTalk Server アプリケーションの開発](../../core/developing-biztalk-server-applications.md)です。
  
-   WCF サービス モデルを使用します。 参照してください[WCF サービス モデルを使用して Siebel アプリケーションを開発](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)です。  
  
-   WCF チャネル モデルを使用します。 WCF チャネル モデルを使用して Oracle データベース アプリケーションの開発を参照してください[リンクは、ここの説明を入力](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [アダプターは、Siebel システムにどのように接続しますか。](https://msdn.microsoft.com/library/cc185212(v=bts.10).aspx)  
  
-   [アダプターのサーフェス Siebel メタデータがどのようにしますか。](https://msdn.microsoft.com/library/cc185267(v=bts.10).aspx)  
  
-   [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)  
  
-   [アダプターでサポートされているその他の機能](https://msdn.microsoft.com/library/cc185252(v=bts.10).aspx) 
  
## <a name="see-also"></a>参照  
 [Siebel eBusiness Applications の BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)