---
title: "Siebel システムとアダプター間のセキュリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, IPsec
- connection URI
- security considerations, between the Siebel system and the adapter
ms.assetid: 40b03d4e-f489-4dce-ba7b-6b6f394275ac
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb9ced17c00432039ff3b85ac85d56e1b6031049
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="security-between-the-siebel-system-and-the-adapter"></a>Siebel システムとアダプター間のセキュリティ
## <a name="encryption-and-authentication"></a>暗号化と認証
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システムで交換されるデータに対する rsa または mscrypto 暗号化をサポートすることができます。 接続 URI では、クエリ文字列パラメーターから暗号化モードを構成します。 Siebel 接続 URI の詳細については、次を参照してください。[作成 Siebel システム接続 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。 Siebel が rsa および mscrypto 暗号化のサポートの詳細については、Siebel のドキュメントを参照してください。  
  
 暗号化モードを指定すると、アダプターと Siebel システム間で交換されるデータのプライバシーを確保する役立ちますただし、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]このような交換での承認、認証、またはデータの整合性をサポートするメカニズムは提供されません。 これらの問題が問題にならなければ、環境内の場合は、それらを軽減するセキュリティ メカニズムを提供する必要があります。  
  
 ネットワーク経由で複数のセキュリティを提供することの 1 つの可能なメカニズムは、インターネット プロトコル セキュリティ (IPsec) です。 IPsec は、オープン標準インターネット プロトコル (IP) ネットワーク経由で通信を保護するためのフレームワークです。 IPsec および Microsoft の製品で IPsec を使用する方法の詳細についてを参照してください"IPsec"Microsoft TechNet の記事で[http://go.microsoft.com/fwlink/?LinkID=196851](http://go.microsoft.com/fwlink/?LinkID=196851)です。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を通じてユーザー名パスワードの資格情報を指定する、Siebel システムに、確立された接続での認証と承認をサポートしています。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]これらの資格情報を使用して接続が開くときに、Siebel システムのユーザーを認証します。 これらの資格情報は、Siebel システムに接続を承認レベルを提供します。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]さまざまなメソッドを使用するには、これらの資格情報を指定することができます。 安全に BizTalk ソリューションで Siebel の資格情報を提供する方法については、次を参照してください。 [Siebel アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)です。 安全にプログラミング ソリューションで Siebel システムの資格情報を提供する方法については、次を参照してください。 [Siebel アダプターをセキュリティで保護された使用したプログラミング](../../adapters-and-accelerators/adapter-siebel/secure-programming-with-the-siebel-adapter.md)です。  
  
> [!NOTE]
>  によって使用される資格情報、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel への接続を確立するためにメッセージ レベルまたはトランスポート レベルの認証または承認、ネットワーク上で送信されるデータをシステムは提供されません。 接続を開くし、Siebel システムでユーザーを認証にのみ使用されます。  
  
## <a name="see-also"></a>参照  
[Siebel アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-siebel/secure-your-siebel-applications.md)