---
title: Siebel システムとアダプター間のセキュリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, IPsec
- connection URI
- security considerations, between the Siebel system and the adapter
ms.assetid: 40b03d4e-f489-4dce-ba7b-6b6f394275ac
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f150e0bb7518d1ce52ed664c63371c48a8b58b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370913"
---
# <a name="security-between-the-siebel-system-and-the-adapter"></a>Siebel システムとアダプター間のセキュリティ
## <a name="encryption-and-authentication"></a>暗号化と認証
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel システムと交換されるデータに rsa または mscrypto の暗号化をサポートできます。 接続 URI で、クエリ文字列パラメーターで暗号化モードを構成するとします。 Siebel 接続 URI の詳細については、次を参照してください。 [、の Siebel システムの接続 URI を作成する](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)します。 Siebel が rsa および mscrypto 暗号化のサポートの詳細については、Siebel のドキュメントを参照してください。  
  
 暗号化モードを指定すると、アダプターと Siebel システム間で交換されるデータのプライバシーを確保する役立ちますただし、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]でこのような交換承認、認証、またはデータの整合性をサポートするメカニズムを提供できません。 これらの問題が環境内の問題となっている場合は、それらを軽減するために、セキュリティ メカニズムを提供する必要があります。  
  
 1 つの可能なメカニズムをネットワーク経由で複数のセキュリティを提供することは、インターネット プロトコル セキュリティ (IPsec) です。 IPsec は、オープンな標準インターネット プロトコル (IP) ネットワーク経由で通信を保護するためのフレームワークです。 IPsec および Microsoft 製品で IPsec を使用する方法の詳細についてを参照してください、Microsoft TechNet の記事"IPsec" [ http://go.microsoft.com/fwlink/?LinkID=196851](http://go.microsoft.com/fwlink/?LinkID=196851)します。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を指定するユーザー名パスワード資格情報を使用して Siebel システムと、確立された接続の承認と認証をサポートしています。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]これらの資格情報を使用して接続を開くときに、Siebel システムのユーザーを認証します。 これらの資格情報は、接続の Siebel システムでの承認レベルを提供します。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]さまざまなメソッドを使用するには、これらの資格情報を指定できます。 安全に BizTalk ソリューションで Siebel の資格情報を提供する方法については、次を参照してください。 [Siebel アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)します。 安全にソリューションをプログラミングで Siebel システムの資格情報を提供する方法については、次を参照してください。 [Siebel アダプターを使用した安全なプログラミング](../../adapters-and-accelerators/adapter-siebel/secure-programming-with-the-siebel-adapter.md)します。  
  
> [!NOTE]
>  使用する資格情報、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel への接続を確立するためにメッセージ レベルまたはトランスポート レベルの認証または承認、ネットワーク上で送信されるデータをシステムは提供されません。 接続を開くし、Siebel システムのユーザーを認証にのみ使用されます。  
  
## <a name="see-also"></a>参照  
[Siebel アプリケーションをセキュリティで保護する](../../adapters-and-accelerators/adapter-siebel/secure-your-siebel-applications.md)