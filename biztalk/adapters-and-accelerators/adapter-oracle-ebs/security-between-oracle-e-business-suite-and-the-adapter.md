---
title: Oracle E-business Suite とアダプター間のセキュリティ |Microsoft ドキュメント
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
ms.openlocfilehash: 5ceac01c8d495374470bf2a78912908338611180
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216394"
---
# <a name="security-between-oracle-e-business-suite-and-the-adapter"></a>Oracle E-business Suite とアダプター間のセキュリティ
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支援と Oracle データベースとの通信を保護するためのサポートはありません。 適切なレベルの承認、認証、データのプライバシー、およびアダプターと Oracle データベースの間のデータ交換用のデータの整合性を確保するセキュリティ メカニズムを提供する必要があります。  
  
 ネットワーク経由で複数のセキュリティを提供することの 1 つの可能なメカニズムは、インターネット プロトコル セキュリティ (IPsec) です。 IPsec は、オープン標準インターネット プロトコル (IP) ネットワーク経由で通信を保護するためのフレームワークです。 IPsec および Microsoft の製品で IPsec を使用する方法の詳細についてを参照してください"IPsec"Microsoft TechNet の記事で[http://go.microsoft.com/fwlink/?LinkID=196851](http://go.microsoft.com/fwlink/?LinkID=196851)です。  
  
 ただし、IPsec などのセキュリティ メカニズムがない場合は、管理者が構成ネイティブ Oracle データの暗号化と整合性をアダプターのクライアントと Oracle E-business Suite の間で交換をセキュリティで保護されたデータを確認します。  
  
 ユーザー名パスワード資格情報を指定する必要があります、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]これらの資格情報を使用して接続が開くときに Oracle データベースでユーザーを認証します。 これらの資格情報は、接続の Oracle データベースで承認レベルを提供します。  
  
> [!NOTE]
>  によって使用される資格情報、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]確立するためにメッセージ レベルまたはトランスポート レベルの認証または承認、ネットワーク上で送信されるデータの Oracle データベースでの接続は提供されません。 接続を開くし、Oracle データベースでユーザーを認証にのみ使用されます。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]さまざまなメソッドを使用するには、これらの資格情報を指定することができます。 安全に BizTalk ソリューションでの Oracle 資格情報を提供する方法については、次を参照してください。 [Oracle E-business Suite アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-oracle-ebs/security-with-the-oracle-e-business-suite-adapter-and-biztalk-server.md)です。 安全にプログラミング ソリューションでの Oracle データベースの資格情報を提供する方法については、次を参照してください。[アダプターのセキュリティに関する考慮事項](../../core/security-considerations-for-adapters.md)です。  
  
## <a name="managing-audit-logs"></a>監査ログを管理します。  
 監査ログでは、エンタープライズ ソフトウェアとにより利用状況の監視と問題の追跡にさまざまなクライアントによって行われた操作に関する情報を格納できます。 ただし、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business suite アダプター クライアントによって実行されるアクションの監査ログを管理する任意の方法を提供しません。 これにより、アダプター クライアントが Oracle E-business Suite でそれらで実行するアクションを repudiate とセキュリティの脅威が発生する可能性があります。 この問題を軽減するのには、Oracle E-business suite アダプター クライアントによって実行される操作をログに Oracle では、監査証跡を有効にする必要があります。 監査証跡を Oracle を設定する方法については、「Oracle ワークフロー-Oracle E-business Suite プロセス」のホワイト ペーパーを参照してください[http://go.microsoft.com/fwlink/?LinkId=136388](http://go.microsoft.com/fwlink/?LinkId=136388)です。  
  
## <a name="see-also"></a>参照  
 [Oracle EBS アプリケーションのセキュリティ保護します。](secure-your-oracle-ebs-applications.md)  
 [Oracle E-business Suite アダプターをセキュリティで保護するベスト プラクティス](../../adapters-and-accelerators/adapter-oracle-ebs/best-practices-to-secure-the-oracle-e-business-suite-adapter.md)