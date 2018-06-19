---
title: Oracle データベースとアダプター間のセキュリティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, security
- authorization
- credentials, supplying user name password
- authentication
- IPsec
ms.assetid: 09d40a05-3678-4002-9e08-2f97c2d5c686
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb27f87bceaba6039588ddcad6b5dcb2d3ce79ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215706"
---
# <a name="security-between-the-oracle-database-and-the-adapter"></a>Oracle データベースとアダプター間のセキュリティ
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支援と Oracle データベースとの通信を保護するためのサポートはありません。 適切なレベルの承認、認証、データのプライバシー、およびアダプターと Oracle データベースの間のデータ交換用のデータの整合性を確保するセキュリティ メカニズムを提供する必要があります。  
  
 ネットワーク経由で複数のセキュリティを提供することの 1 つの可能なメカニズムは、インターネット プロトコル セキュリティ (IPsec) です。 IPsec は、オープン標準インターネット プロトコル (IP) ネットワーク経由で通信を保護するためのフレームワークです。 IPsec および Microsoft の製品で IPsec を使用する方法の詳細についてを参照してください"IPsec"Microsoft TechNet の記事で[http://go.microsoft.com/fwlink/?LinkId=196851](http://go.microsoft.com/fwlink/?LinkId=196851)です。  
  
 ただし、IPsec などのセキュリティ メカニズムがない場合は、管理者が構成ネイティブ Oracle データの暗号化と整合性をアダプターのクライアントと Oracle データベース間のセキュリティで保護されたデータの交換を確認します。 ネイティブの Oracle データの暗号化と整合性を構成する方法の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/p/?LinkId=140032](http://go.microsoft.com/fwlink/p/?LinkId=140032)です。  
  
 ユーザー名パスワード資格情報を指定する必要があります、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]これらの資格情報を使用して接続が開くときに Oracle データベースでユーザーを認証します。 これらの資格情報は、接続の Oracle データベースで承認レベルを提供します。  
  
> [!NOTE]
>  によって使用される資格情報、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]確立するためにメッセージ レベルまたはトランスポート レベルの認証または承認、ネットワーク上で送信されるデータの Oracle データベースでの接続は提供されません。 接続を開くし、Oracle データベースでユーザーを認証にのみ使用されます。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]さまざまなメソッドを使用するには、これらの資格情報を指定することができます。 安全に BizTalk ソリューションでの Oracle 資格情報を提供する方法については、次を参照してください。 [Oracle データベース アダプターと Biztalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)です。 安全にプログラミング ソリューションでの Oracle データベースの資格情報を提供する方法については、次を参照してください。 [Oracle データベース アダプターを使用したプログラミング セキュリティで保護された](../../adapters-and-accelerators/adapter-oracle-database/secure-programming-with-the-oracle-database-adapter.md)です。  
  
## <a name="managing-audit-logs"></a>監査ログを管理します。  
 監査ログでは、エンタープライズ ソフトウェアとにより利用状況の監視と問題の追跡にさまざまなクライアントによって行われた操作に関する情報を格納できます。 ただし、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]上、Oracle データベース アダプターのクライアントで実行するアクションの監査ログを管理する任意の方法を提供しません。 これにより、アダプター クライアントが Oracle データベースでそれらで実行するアクションを repudiate とセキュリティの脅威が発生する可能性があります。 この問題を軽減するのには、Oracle データベースでアダプター クライアントによって実行される操作をログに Oracle では、監査証跡を有効にする必要があります。  
  
## <a name="see-also"></a>参照  
[Oracle データベース アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)   
[ベスト プラクティス](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)