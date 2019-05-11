---
title: データベースのパフォーマンスの計画 |Microsoft Docs
ms.custom: ''
ms.date: 11/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7212fa37-88e0-4b5f-af97-c72063357645
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cbbf9c072289b177779ed8ae3a991f58b9f26efe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394616"
---
# <a name="planning-for-database-performance"></a>データベース パフォーマンスの計画

## <a name="overview"></a>概要
Microsoft BizTalk Server は、非常にデータベース処理を要するアプリケーションの Microsoft SQL Server にある最大 13 個の異なるデータベースを作成することがあります。 BizTalk Server のデータベース処理を要する性質が原因は非常に重要な適切なバージョンとエディションの BizTalk Server データベースを格納する SQL Server を選択することです。 このトピックの「し、推奨事項に従い BizTalk Server データベースを格納する SQL Server を実行しているコンピューター パフォーマンスを最適化するために、 [BizTalk Server データベースの最適化](optimizing-database-performance.md)します。
  

> [!NOTE]  
>  BizTalk Server と SQL Server の他のバージョンをこのガイドを作成以降のバージョンのと同じ推奨事項を使用できます。
  
## <a name="considerations-for-sql-server-editions"></a>SQL Server のエディションに関する考慮事項  
 BizTalk Server データベースは、可能であれば、専用の SQL Server インスタンス上で実行するように構成する必要があります。 BizTalk Server が処理を要するアプリケーションのデータベース、BizTalk Server コンピューターのための分離と、BizTalk Server データベースを格納する SQL Server コンピューターのパフォーマンスが向上し、運用環境の BizTalk Server でのベスト プラクティスを考慮する必要があります。環境。  
  
 SQL Server のさまざまなエディションでは、BizTalk Server 環境のパフォーマンスに影響を与えるさまざまな機能を提供します。 たとえば、高負荷条件下では SQL Server の 32 ビット バージョンで使用できる使用可能なデータベース ロックの数超過可能性がある、BizTalk ソリューションのパフォーマンスに悪影響は。 テスト環境で"ロック"の範囲外のエラーが発生した場合、64 ビット バージョンの SQL Server でメッセージ ボックス データベースを格納していることを検討してください。 使用可能なロックの数は、64 ビット バージョンの SQL Server で大幅に高くなっています。  
  
 BizTalk 環境に必要なときに、データベース エンジンを決定する機能を次の表を検討してください。 小規模なソリューションは、BizTalk Server の Branch エディションを実行する場合、たとえば SQL Server Workgroup Edition 可能性があります、BizTalk Server データベースを格納するための適切です。 大規模なエンタープライズ レベルのソリューションをクラスタ リングのサポートを必要とする BizTalk ログ配布のサポート、または Analysis Services のサポート、SQL Server の Enterprise Edition のデータベースをホストする必要があります。  
  
|SQL Server のエディション|64 ビットのサポート|複数インスタンスのサポート|クラスタ リングのサポート|Analysis Services|  
|---|---|---|---|---|  
|SQL Server Enterprise Edition|はい|[はい]|[はい]|はい|  
|SQL Server Standard Edition|はい|はい|[はい] (2 ノード)|はい|  
|SQL Server Workgroup Edition|はい|[はい]|いいえ|いいえ|  
  
> [!NOTE]  
>  BAM RTA では、SQL Server Enterprise Edition が必要です。  
  
 各エディションでサポートされる機能の完全な一覧を参照してください。[機能は、SQL Server の各エディションでサポートされている](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016)します。