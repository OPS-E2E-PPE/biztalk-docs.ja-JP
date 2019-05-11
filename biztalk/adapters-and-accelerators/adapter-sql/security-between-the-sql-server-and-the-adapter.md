---
title: SQL Server とアダプター間のセキュリティ |Microsoft Docs
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
ms.openlocfilehash: 3414cb5ed82cc9003e6207c4a58150dd914d2a19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367945"
---
# <a name="security-between-the-sql-server-and-the-adapter"></a>SQL Server とアダプター間のセキュリティ
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]データベース サーバーとのデータ交換をセキュリティで保護するために使用 SSO と IPSEC など、標準の方法と互換性が。 セキュリティ保護されていないデータの交換には、不正なアクターにデータを公開できます。 SQL Server セキュリティ上の問題については、次を参照してください。 [for SQL Server のセキュリティに関する考慮事項](http://go.microsoft.com/fwlink/p/?LinkId=196954)SQL ドキュメント。  
  
 インターネット プロトコル セキュリティ (IPsec) を使用してデータ交換のセキュリティを向上させることができます。 IPsec は、オープンな標準インターネット プロトコル (IP) ネットワーク経由で通信を保護するためのフレームワークです。 すべてのデータは、IPSec の間で交換される、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]と、SQL、ネットワーク経由でサーバーを暗号化すると、不正なアクター データを使用するが難しくなります。 IPsec および Microsoft 製品で IPsec を使用する方法の詳細については、Microsoft TechNet の記事を参照してください。 [IPsec](http://go.microsoft.com/fwlink/p/?LinkId=196955)します。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]データベースと、確立された接続での認証の SSO と統合セキュリティをサポートしています。 Sso、資格情報が暗号化され、レジストリに格納されています。 システムでは、これらの資格情報を使って、不正なアクターによって表示される可能性を入力するように求めるのではなくアクセスを決定します。 統合セキュリティは、SQL server へのアクセスにログオンしたユーザーの資格情報を使用します。 これもユーザー資格情報を入力する必要はありません。 データベース管理者を正常に動作する統合セキュリティのユーザーの資格情報を受け入れるように SQL を構成する必要があります。  
  
## <a name="see-also"></a>参照  
[SQL アプリケーションをセキュリティで保護する](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)