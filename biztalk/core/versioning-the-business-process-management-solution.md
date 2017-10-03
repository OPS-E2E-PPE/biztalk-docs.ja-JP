---
title: "ビジネス プロセス管理ソリューションのバージョン管理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- versioning, process management solutions
- process management solution tutorial, modifying
- process management solution tutorial, versioning
- processing, stages
- process management solution tutorial, processing stages
ms.assetid: 501b2162-821f-44e1-87c0-8628cc5bd9c3
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af8afd3666a35b827ff25b243c1bfb4c81262273
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="versioning-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションのバージョン管理
ビジネス プロセス管理ソリューションは、必要に応じてステージを置換できるように設計されています。 スキーマのバージョンを簡単に管理する機能も備えています。  
  
 ビジネス プロセスをステージに分割する方法については、次を参照してください。[ビジネス プロセス管理ソリューションで一部の設計原則](../core/some-design-principles-in-the-business-process-management-solution.md)です。  
  
> [!NOTE]
>  ソリューションの要素は、メッセージ構造に大きく依存します。 メッセージ構造を変更するには、オーケストレーションを大幅に変更する必要があります。  
  
 配置されたソリューションとスクリプトの記述に関するガイドラインの更新を処理するアセンブリの更新に関する一般的な手順については、次を参照してください。 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)です。  
  
## <a name="adding-replacing-or-removing-stages"></a>ステージの追加、置換、または削除  
 注文処理ステージ オーケストレーションは、2 種類のコードを含める: ビジネス プロセスと、ソリューション内に操作できるように、インフラストラクチャを提供するコードを実装するコードです。 ステージ オーケストレーションの両方で**CableOrder1**と**CableOrder2**、ビジネス プロセス コード グループ図形内のラベルは「ビジネス処理します」。  
  
 新しい段階を作成する最も簡単な方法では、登録、「ビジネス プロセス」グループ内のコードをコードに置き換えますをインフラストラクチャ コードをそのまま残す段階の 1 つをコピーします。  
  
> [!NOTE]
>  **CableOrder2**オーケストレーションは、「ビジネス プロセス」の 2 つのグループ、2 番目は Update History Send 図形です。 送信図形は、効率的な送信スコープの一部です。 (詳細についてを参照してください「向上パフォーマンスで入れ子になったスコープ」 [OrderBroker オーケストレーションで処理](../core/processing-in-the-orderbroker-orchestration.md))。グループ図形はスコープ図形の一部と重ねることができないので、2 番目のグループにはビジネス プロセス コードの一部であることを示すラベルが付けられます。  
  
 新しいオーケストレーションのフィルタ式に連番を設定する必要があります。 **OrderManager**ステージ番号が 1 つで始まり、各次のステージ (1, 2, 3...) の 1 つ増やしますを前提としています。 3 番目のステージをフィルタリングするには、フィルタ式を次のように設定する必要があります。  
  
 `(Microsoft.Samples.BizTalk.SouthridgeVidoe.Schemas.Stage == 3)`  
  
 ソリューションは、BAM API を使用して、注文処理ステージなどソリューション内のイベントを追跡します。 最初のステージで BAM アクティビティが開始され、最終ステージで終了します。 例外が発生した場合、ソリューション内のハンドラは BAM 関連アクティビティを終了させます。 BAM は不連続の操作を効果的にまとめて、1 つの連続したビューとして監視できるようにします。  
  
## <a name="changing-configuration"></a>構成の変更  
 変更によりステージ数が増減する場合は、エンタープライズ シングル サインオン (SSO) シークレット ストアに格納された構成情報を変更する必要があります。  
  
 アプリケーションを展開していない場合は、構成設定を変更することができます**TotalStages** CreateSouthridgeVideoApplication.cmd スクリプト ファイルにします。 展開時にスクリプトが実行されると、値が変更されます。  
  
 アプリケーションが展開済みである場合、SDK\Common\SsoApplicationConfig フォルダのコマンド ライン ユーティリティ BTSScnSSOApplicationConfig を実行することによって値を変更できます。 ステージの合計数を 3 に設定するには、次のコマンド ラインを使用します。  
  
 `BTSScnSSOApplicationConfig -set SouthRidgeVideo.CableOrder ConfigProperties TotalStages 3`  
  
 構成値はキャッシュされるので、新しい値が有効になるには、キャッシュ更新間隔が経過するのを待つ必要があります。  
  
## <a name="versioning-schemas"></a>バージョン管理スキーマ  
 BizTalk は、スキーマを含むアセンブリの最新バージョンからスキーマを取得します。 つまり、スキーマの新しいバージョンを作成すると、スキーマのすべての旧バージョンが置き換えられるということです。 これは、短期間のトランザクションの場合に有効です。 ただし、ビジネス プロセス管理ソリューション内のトランザクションは有効期間が長い: 注文かかる場合があります、年を完了します。  
  
 スキーマの複数のバージョンが使用される可能性を考慮して、ソリューションの各スキーマは名前空間にバージョン番号を含んでいます。 たとえば、注文スキーマの名前空間は次のようになっています。  
  
```  
http://Microsoft.Samples.BizTalk.SouthridgeVideo.Schemas.Order.v1  
```  
  
 名前空間がスキーマを識別し、バージョン番号を含めることで名前空間がスキーマに対して一意になっているので、新しいスキーマを旧バージョンと区別できます。 したがって、古いスキーマを置き換えずに新しいスキーマを使用できます。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの開発](../core/developing-a-business-process-management-solution.md)