---
title: "データベースのパフォーマンスの計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7212fa37-88e0-4b5f-af97-c72063357645
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 878320cf7c6a5762626087964033430afcf611cf
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="planning-for-database-performance"></a>データベースのパフォーマンスの計画

## <a name="overview"></a>概要
Microsoft BizTalk Server は非常に高くデータベース処理を要するアプリケーションの Microsoft SQL Server に最大 13 個ある異なるデータベースの作成が必要な場合があります。 BizTalk Server のデータベース処理を要する性質があるためには重要な意味、適切なバージョンと、BizTalk Server データベースを格納する SQL Server のエディションを選択することです。 BizTalk Server データベースを格納する SQL Server を実行しているコンピューターのパフォーマンスを最適化する」を参照し、推奨事項に従い、 [BizTalk Server データベースの最適化](optimizing-database-performance.md)です。
  

> [!NOTE]  
>  このガイドは、BizTalk Server と SQL Server の他のバージョンの書き込みは、中に新しいバージョンを同じの推奨事項を使用できます。
  
## <a name="considerations-for-sql-server-editions"></a>SQL Server のエディションに関する考慮事項  
 BizTalk Server データベースは、できるだけ専用の SQL Server インスタンス上で実行するように構成する必要があります。 BizTalk Server は、データベースの処理を要するアプリケーションを BizTalk Server コンピューターのための分離と、BizTalk Server データベースを格納する SQL Server コンピューターが、パフォーマンスが向上し、実稼働の BizTalk Server ではベスト プラクティスを考慮する必要があります。環境。  
  
 SQL Server の各種エディションでは、BizTalk Server 環境のパフォーマンスが低下する可能性が別の機能を提供します。 たとえば、高負荷条件下で 32 ビット バージョンの SQL Server で利用可能な使用可能なデータベース ロックの数可能性があるを超えると、これは、BizTalk ソリューションのパフォーマンスを低下させます。 テスト環境でロックの範囲外"エラーが発生した場合、64 ビット バージョンの SQL Server にメッセージ ボックス データベースを格納していることを検討してください。 64 ビット バージョンの SQL Server では、使用できるロックの数が大幅に増えます。  
  
 BizTalk 環境に必要な機能するとき、データベース エンジンの決定を下にあるテーブルを検討してください。 小規模なソリューションは、BizTalk Server Branch エディションを実行する場合、たとえば SQL Server Workgroup Edition 可能性があります、BizTalk Server データベースを格納する適切です。 大規模なエンタープライズ レベルのソリューションをクラスタ リングのサポートを必要とする BizTalk ログ配布のサポート、または Analysis Services のサポート、SQL Server Enterprise Edition のデータベースをホストする必要があります。  
  
|SQL Server のエディション|64 ビットのサポート|複数インスタンスのサポート|クラスタ リングのサポート|Analysis Services|  
|---|---|---|---|---|  
|SQL Server Enterprise Edition|可|可|可|可|  
|SQL Server Standard Edition|可|可|[はい] (2 ノード)|可|  
|SQL Server Workgroup Edition|可|可|いいえ|不可|  
  
> [!NOTE]  
>  BAM RTA では、SQL Server Enterprise Edition が必要です。  
  
 各エディションでサポートされる機能の完全な一覧を参照してください。 [SQL Server のエディションでサポートされる機能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016)します。