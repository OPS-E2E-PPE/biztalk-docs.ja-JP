---
title: アダプターを使用して SQL Server への接続 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 727d73e6-fb84-48ce-ae72-5de70dcae8b8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9b837aa4e0bc0a815434307b10d249dccf54d70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222138"
---
# <a name="connect-to-sql-server-using-the-adapter"></a>アダプターを使用して SQL Server への接続します。
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]アダプター クライアント識別子 URI (Uniform Resource)、SQL Server データベースに接続する接続と呼ばれる、接続文字列を指定する必要があります。 内部的には、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] URI を SQL Server データベースに接続するデータベース接続文字列にマップします。 接続 URI のアダプターのクライアントは、外部システムに接続するための接続パラメーターを指定できます。 接続 URI の詳細については、次を参照してください。 [SQL Server の接続 URI を作成する](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。  
  
 URI の接続で、フェールオーバーの SQL Server データベースの名前をプライマリ SQL Server データベースが使用できない場合に接続するスタンバイ コンピューター上も指定できます。 フェールオーバーの SQL Server データベースには、プライマリ SQL Server データベースのミラーをする必要があります。 パラメーターを使用して、省略可能な FailoverPartner 接続 URI でフェールオーバーの SQL Server データベースが指定されました。 高可用性とデータの冗長性、フェールオーバーの SQL Server データベースを提供することを確認します。 SQL Server に対する高可用性の詳細については、次を参照してください。 [SQL Server でデータベース ミラーリング](https://msdn.microsoft.com/library/5h52hef8.aspx)です。
  
 SQL Server データベースとの接続を確立するときに、セキュリティのガイドラインに従うことを確認します。 セキュリティに関するガイドラインの詳細については、次を参照してください。 [SQL アプリケーションのセキュリティ保護](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for SQL Server の概要](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)   
 [SQL Server への接続を作成します。](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md)