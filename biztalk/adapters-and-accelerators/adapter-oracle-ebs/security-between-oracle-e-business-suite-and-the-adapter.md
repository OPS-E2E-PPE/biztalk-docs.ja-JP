---
title: Oracle E-business Suite とアダプター間のセキュリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88f5f8ed-48d5-4420-9fdb-0a6860b95ac4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ed940484143038ba6666dedf7d7ae445f6f5911
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374583"
---
# <a name="security-between-oracle-e-business-suite-and-the-adapter"></a>Oracle E-business Suite とアダプター間のセキュリティ
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]はサポートしていません、Oracle データベースとの間のセキュリティで保護された通信を支援します。 適切なレベルの承認、認証、データ プライバシー、およびアダプターと Oracle データベースの間のデータ交換用のデータの整合性を確保しやすく、セキュリティ メカニズムを提供する必要があります。  
  
 1 つの可能なメカニズムをネットワーク経由で複数のセキュリティを提供することは、インターネット プロトコル セキュリティ (IPsec) です。 IPsec は、オープンな標準インターネット プロトコル (IP) ネットワーク経由で通信を保護するためのフレームワークです。 IPsec および Microsoft 製品で IPsec を使用する方法の詳細についてを参照してください、Microsoft TechNet の記事"IPsec" [ http://go.microsoft.com/fwlink/?LinkID=196851](http://go.microsoft.com/fwlink/?LinkID=196851)します。  
  
 ただし、IPsec などのセキュリティ メカニズムがない場合、管理者が構成ネイティブの Oracle データの暗号化と整合性のアダプターのクライアントと Oracle E-business Suite の間のセキュリティで保護されたデータ交換を確認します。  
  
 ユーザー名パスワード資格情報を指定する必要があります、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接続を開くときに、Oracle データベースでユーザーの認証にこれらの資格情報を使用します。 これらの資格情報は、接続の Oracle データベースでの承認レベルを提供します。  
  
> [!NOTE]
>  使用する資格情報、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を確立するメッセージ レベルまたはトランスポート レベルの認証または承認、ネットワーク上で送信されるデータを Oracle データベースでの接続は提供されません。 接続を開くし、Oracle データベースでユーザーを認証にのみ使用されます。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]さまざまなメソッドを使用するには、これらの資格情報を指定できます。 安全に BizTalk ソリューションでの Oracle 資格情報を提供する方法については、次を参照してください。 [Oracle E-business Suite アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-oracle-ebs/security-with-the-oracle-e-business-suite-adapter-and-biztalk-server.md)します。 安全にソリューションをプログラミングでの Oracle データベースの資格情報を提供する方法については、次を参照してください。[アダプターのセキュリティに関する考慮事項](../../core/security-considerations-for-adapters.md)します。  
  
## <a name="managing-audit-logs"></a>監査ログを管理します。  
 監査ログでは、エンタープライズ ソフトウェア、およびにより使用状況の監視と問題追跡のさまざまなクライアントによって実行されたアクションに関する情報を格納できます。 ただし、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business suite アダプター クライアントによって実行されたアクションの監査ログを管理する任意の方法を提供しません。 これにより、アダプターのクライアントが Oracle E-business Suite で、それらによって実行されたアクションを repudiate とセキュリティの脅威が発生する可能性があります。 この問題を軽減するには、oracle で Oracle E-business Suite アダプター クライアントによって実行される操作をログに監査記録を有効にする必要があります。 Oracle を設定する方法については監査証跡、「Oracle ワークフロー-Oracle E-business Suite プロセス」のホワイト ペーパーを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=136388](http://go.microsoft.com/fwlink/?LinkId=136388)します。  
  
## <a name="see-also"></a>参照  
 [Oracle EBS アプリケーションをセキュリティで保護する](secure-your-oracle-ebs-applications.md)  
 [Oracle E-business Suite アダプターをセキュリティで保護するベスト プラクティス](../../adapters-and-accelerators/adapter-oracle-ebs/best-practices-to-secure-the-oracle-e-business-suite-adapter.md)