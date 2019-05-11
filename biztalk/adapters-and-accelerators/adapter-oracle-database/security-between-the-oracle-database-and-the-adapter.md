---
title: Oracle データベースとアダプター間のセキュリティ |Microsoft Docs
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
ms.openlocfilehash: 54325612ce61ca3d351e33223924c9b899e11902
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376015"
---
# <a name="security-between-the-oracle-database-and-the-adapter"></a>Oracle データベースとアダプター間のセキュリティ
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]はサポートしていません、Oracle データベースとの間のセキュリティで保護された通信を支援します。 適切なレベルの承認、認証、データ プライバシー、およびアダプターと Oracle データベースの間のデータ交換用のデータの整合性を確保しやすく、セキュリティ メカニズムを提供する必要があります。  
  
 1 つの可能なメカニズムをネットワーク経由で複数のセキュリティを提供することは、インターネット プロトコル セキュリティ (IPsec) です。 IPsec は、オープンな標準インターネット プロトコル (IP) ネットワーク経由で通信を保護するためのフレームワークです。 IPsec および Microsoft 製品で IPsec を使用する方法の詳細についてを参照してください、Microsoft TechNet の記事"IPsec" [ http://go.microsoft.com/fwlink/?LinkId=196851](http://go.microsoft.com/fwlink/?LinkId=196851)します。  
  
 ただし、IPsec などのセキュリティ メカニズムがない場合、管理者が構成ネイティブ Oracle データの暗号化と整合性のアダプターのクライアントと Oracle データベースの間のセキュリティで保護されたデータ交換を確認します。 ネイティブの Oracle データの暗号化および整合性を構成する方法の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/p/?LinkId=140032](http://go.microsoft.com/fwlink/p/?LinkId=140032)します。  
  
 ユーザー名パスワード資格情報を指定する必要があります、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接続を開くときに、Oracle データベースでユーザーの認証にこれらの資格情報を使用します。 これらの資格情報は、接続の Oracle データベースでの承認レベルを提供します。  
  
> [!NOTE]
>  使用する資格情報、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を確立するメッセージ レベルまたはトランスポート レベルの認証または承認、ネットワーク上で送信されるデータを Oracle データベースでの接続は提供されません。 接続を開くし、Oracle データベースでユーザーを認証にのみ使用されます。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]さまざまなメソッドを使用するには、これらの資格情報を指定できます。 安全に BizTalk ソリューションでの Oracle 資格情報を提供する方法については、次を参照してください。 [Oracle データベース アダプターと Biztalk Server でセキュリティ](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)します。 安全にソリューションをプログラミングでの Oracle データベースの資格情報を提供する方法については、次を参照してください。 [Oracle データベース アダプターを使用したプログラミングにセキュリティで保護された](../../adapters-and-accelerators/adapter-oracle-database/secure-programming-with-the-oracle-database-adapter.md)します。  
  
## <a name="managing-audit-logs"></a>監査ログを管理します。  
 監査ログでは、エンタープライズ ソフトウェア、およびにより使用状況の監視と問題追跡のさまざまなクライアントによって実行されたアクションに関する情報を格納できます。 ただし、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベース アダプターのクライアントによって実行されたアクションの監査ログを管理する任意の方法を提供しません。 これにより、アダプターのクライアントが Oracle データベースで、それらによって実行されたアクションを repudiate とセキュリティの脅威が発生する可能性があります。 この問題を軽減するには、oracle で Oracle データベース アダプターのクライアントによって実行される操作をログに監査記録を有効にする必要があります。  
  
## <a name="see-also"></a>参照  
[Oracle データベース アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)   
[ベスト プラクティス](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)