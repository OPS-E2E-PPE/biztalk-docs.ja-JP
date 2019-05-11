---
title: アダプターを使用して SQL Server への接続 |Microsoft Docs
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
ms.openlocfilehash: b11db610e76a6bac856b8104506f64e4539cf6ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369928"
---
# <a name="connect-to-sql-server-using-the-adapter"></a>アダプターを使用して SQL Server に接続します。
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]アダプター クライアント接続の Uniform Resource Identifier (URI) を SQL Server データベースへの接続と呼ばれる接続文字列を指定する必要があります。 内部的には、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] URI を SQL Server データベースに接続するデータベース接続文字列にマップされます。 接続 URI では、アダプター クライアントは、外部システムに接続する接続パラメーターを指定できます。 接続 URI の詳細については、次を参照してください。 [SQL Server の接続 URI の作成](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。  
  
 URI の接続でスタンバイ プライマリ SQL Server データベースが使用できない場合に接続するコンピューターのフェールオーバーの SQL Server データベースの名前を指定することもできます。 フェールオーバーの SQL Server データベースには、プライマリ SQL Server データベースのミラーをする必要があります。 パラメーターを使用して、省略可能な FailoverPartner 接続 URI で、フェールオーバー SQL Server データベースが指定されました。 フェールオーバーの SQL Server データベースを提供することにより、高可用性とデータの冗長性。 高可用性の SQL Server についての詳細については、次を参照してください。 [SQL Server データベースのミラーリング](https://msdn.microsoft.com/library/5h52hef8.aspx)します。
  
 SQL Server データベースとの接続を確立するときに、セキュリティのガイドラインに従うことを確認します。 セキュリティのガイドラインの詳細については、次を参照してください。 [SQL アプリケーションのセキュリティ保護](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for SQL Server の概要](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)   
 [SQL Server への接続を作成します。](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md)