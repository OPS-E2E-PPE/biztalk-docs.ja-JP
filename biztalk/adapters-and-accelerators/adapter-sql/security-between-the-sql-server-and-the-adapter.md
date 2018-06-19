---
title: SQL Server とアダプター間のセキュリティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4b0fd11-6753-4f52-9be7-3b6fa330fb8b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8673aee316a8a2ef83011ab3dd85016a99df1162
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222498"
---
# <a name="security-between-the-sql-server-and-the-adapter"></a>SQL Server とアダプター間のセキュリティ
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]と互換性が標準の方法では、データベース サーバーとデータ交換をセキュリティで保護するために使用 SSO と IPSEC などです。 セキュリティ保護されていないデータの交換には、承認されていないアクターにデータを公開できます。 SQL Server のセキュリティに関する問題については、次を参照してください。 [for SQL Server のセキュリティに関する考慮事項](http://go.microsoft.com/fwlink/p/?LinkId=196954)SQL のドキュメントにします。  
  
 インターネット プロトコル セキュリティ (IPsec) を使用して、データ交換のセキュリティを向上させることができます。 IPsec は、オープン標準インターネット プロトコル (IP) ネットワーク経由で通信を保護するためのフレームワークです。 すべてのデータは、IPSec の間で交換される、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]と SQL ネットワーク経由でサーバーを暗号化すると、データを使用するアクターが承認されていないのは困難になります。 IPsec および Microsoft の製品で IPsec を使用する方法の詳細については、Microsoft TechNet の記事を参照してください。 [IPsec](http://go.microsoft.com/fwlink/p/?LinkId=196955)です。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]データベースと、確立された接続での認証に、SSO と統合セキュリティをサポートしています。 SSO を使用して資格情報は暗号化し、レジストリに格納されています。 システムでは、これらの資格情報を使用して、未承認のアクターによって認識がそれらを入力するユーザーを要求する代わりに、アクセスを決定します。 統合セキュリティは、SQL server へのアクセスにログオンしたユーザーの資格情報を使用します。 これは、ユーザーが資格情報を入力する必要もなくなります。 データベース管理者を正常に動作する統合セキュリティのユーザーの資格情報を受け入れるように SQL を構成する必要があります。  
  
## <a name="see-also"></a>参照  
[SQL アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)