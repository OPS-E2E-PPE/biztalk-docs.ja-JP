---
title: ビジネス プロセス管理ソリューションを理解する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solutions, resources
- process management solutions, applications
- process management solution tutorial, background information
- process management solutions, about process management solutions
- applications, process management solutions
ms.assetid: fa6ad8d2-08d7-4770-9394-835f99bfd146
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9759f6521297377b204f0695a511de40d22a830d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287906"
---
# <a name="understanding-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションについて
このセクションで説明するソリューションは、ビジネス プロセス管理アプリケーションを実装する方法を示します。 理想的なビジネス プロセス マネージャでは、ソリューションの各部分が、ビジネス ルール、特定のバックエンド システムとの通信、応答メッセージの送信などのビジネス プロセスを表し、プロセスを支えるインフラストラクチャと分離されています。  
  
 この "Southridge Video のケーブル サービス注文システム" ソリューションでは、ビジネス プロセスが一連のステージに分割されています。 これらのステージに対する操作は、ビジネス ルールやバックエンド システムについて何ら知識のない注文マネージャによって指示されます。 注文マネージャは、注文ブローカから注文を受け取ります。注文ブローカは複数の異なる注文マネージャに注文を送信できます。  
  
 このソリューションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の機能を広く利用し、特にアプリケーションの各部を調整するためにアプリケーション内部のメッセージを使用する方法を示します。  
  
## <a name="reader-guidance"></a>対象読者  
 このドキュメントが慣れていることを前提と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。 また、エンタープライズ アプリケーション統合と Web サービスの基本的な概念についても理解していることを前提としています。  
  
 さらに、開発者向けのマニュアルを読み、理解するためには、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用してアプリケーションを構築する方法や、プロジェクトの作成、参照の設定、BizTalk ソリューションのデバッグおよびテストなどのタスクについても精通している必要があります。  
  
## <a name="ordering-cable-service-from-southridge-video"></a>Southridge Video のケーブル サービスの注文  
 ビジネス プロセス管理ソリューションは、Southridge Video のケーブル サービス注文システムを実装します。 顧客がコール センターに電話すると、顧客サービス担当者が注文を受け、注文システムに入力します。 次の図では、システムにおける注文の全体的な流れを示しています。  
  
 ![ビジネス プロセス管理ソリューションのワークフロー](../core/media/business-process-manager-solution-work-flow.gif "Business_Process_Manager_Solution_Work_Flow")  
  
 注文は、注文ブローカに送られ、そこから注文マネージャに送信されます。 注文マネージャは正しい順序で処理ステージを実行し、注文を処理します。 特定の種類のエラーはオペレーション センターに送られ、修正され、再送信されること、およびソリューションでは SQL Server テーブルに各注文の履歴が記録されることに注意してください。  
  
 次の図では、注文を処理する手順の概要を示しています。  
  
 ![ビジネス プロセス管理ソリューションのシーケンス](../core/media/business-process-manager-solution-sequence.gif "Business_Process_Manager_Solution_Sequence")  
  
 注文は更新される場合や取り消される場合があることに注意してください。  
  
## <a name="business-requirements"></a>ビジネス要件  
 ビジネス プロセス管理ソリューションは、ケーブル サービス業者である Southridge Video の注文システムの例を示します。 Microsoft BizTalk Server にプロセス マネージャ パターンを実装する方法を示しています。 このソリューションでは、オーケストレーションを使用して、ビジネス プロセスを実行する 2 つのサテライト オーケストレーションを介した注文の流れを管理します。 この構造は、ソリューションの次のようなビジネス要件に基づいています。  
  
-   ビジネス プロセスのバージョン管理を行う。  
  
-   長期にわたる注文を処理する。  
  
-   処理中の注文を変更またはキャンセルする (注文に対する補足処理)。  
  
-   保留注文を避ける。  
  
-   プロセス全体で注文を追跡する。  
  
-   注文を一括処理する。  
  
-   リモート データ センターからの注文を受け付ける。  
  
-   複数のグループが注文処理の各部分を処理できる。  
  
-   BizTalk グループを追加してアプリケーションを拡張する。  
  
-   リモート処理により、注文マネージャをアプリケーション サーバーとして公開する。  
  
 Southridge Video のビジネス要件では、注文ブローカ、プロセス マネージャ、およびビジネス プロセスの 3 つの部分による構造になります。 Southridge Video には、アプリケーションに関与する IT グループが 2 つあります。 メッセージング グループは、企業メッセージング インフラストラクチャを管理し、そのインフラストラクチャにアプリケーションを接続するためのコンポーネントを提供します。 もう一方のグループは、特定のビジネス プロセスのアプリケーションを作成し、管理します。 したがって、注文ブローカは、独立したグループで管理できるように、注文プロセス マネージャおよびプロセス ステージから分離します。 注文ブローカは独立したコンポーネントであるため、複数のプロセス マネージャへの注文を仲介できるように拡張することもできます。 プロセス マネージャを追加すると、VIP サービスなどの新しいビジネス ラインをサポートすることができます。  
  
 Southridge Video の注文は、長期プロセスです。ケーブル注文が完了するまでに要する時間は、1 分から 1 年までさまざまです。 BizTalk オーケストレーションのインスタンスは完了するまで実行される必要があるため、オーケストレーション インスタンスの有効期間は最長で 1 年になる場合があります。  
  
 Southridge Video は、注文処理中にアプリケーション コンポーネントを変更できるような、長期プロセスに対応したアーキテクチャを必要としています。 このため、最新のプロセス コンポーネントを使用して注文を完了できるように、Southridge では注文処理を複数のステージに分割しました。 ビジネス プロセスにおいてステージの境界を決定する方法については、次を参照してください。[ビジネス プロセス管理ソリューションで一部の設計原則](../core/some-design-principles-in-the-business-process-management-solution.md)です。  
  
 注文の処理時間が長いことも、処理中の注文の変更が必要になる要因です。 注文の変更は、ソリューションに広範な割り込みシステムが組み込まれている理由の 1 つです。 割り込みシステムを組み込むと、完了していない注文を簡単に変更またはキャンセルできます。 ソリューションでは、割り込みを処理するためのソリューションの各機能間の通信に .NET メッセージを使用します。  
  
 システムには、いくつもの外部依存関係があるため、エラー後に再試行される操作もあります。 たとえば、バックエンド システムを使用できず、それに対する要求がタイムアウトになると、ソリューションでは、適切な時間待機し、要求を再度実行します。 外部システムへの接続はカスタム コードによるため、ソリューションのその部分ではオブジェクト メソッドを再試行できるように、.NET リフレクションを広範に使用します。  
  
 このソリューションでは、基になっている実際の会社と同じように、オペレーション グループの担当者が注文処理に関する問題を処理できることを前提としています。 同様に、顧客サービス担当者に返される注文エラーもあります。顧客サービス担当者は、その注文をキャンセルするか、修正して再送信します。  
  
## <a name="business-process-management-solution-resources"></a>ビジネス プロセス管理ソリューションのリソース  
 ビジネス プロセス管理ソリューションの詳細については、次のドキュメントをお読みください。  
  
### <a name="business-process-management-solution-resources"></a>ビジネス プロセス管理ソリューションのリソース  
  
-   [ビジネス プロセス管理ソリューションの開発](../core/developing-a-business-process-management-solution.md)  
  
     開発者やソフトウェア設計者は、このガイドを使用して、ビジネス プロセス管理アプリケーションの構築と実行に必要なすべてのコード、パターン、アーキテクチャ、およびパフォーマンス デザインを記述できます。  
  
-   [ビジネス プロセス管理ソリューションの展開](../core/deploying-the-business-process-management-solution.md)  
  
     BizTalk Server の一般知識を持っている IT プロフェッショナルは、このガイドを使用してビジネス プロセス管理アプリケーションを構築し、実行できます。 このガイドは、ユーザーが、分散環境でのアプリケーションの機能に関する一般的な知識を持っていることを前提としています。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューション](../core/business-process-management-solution.md)