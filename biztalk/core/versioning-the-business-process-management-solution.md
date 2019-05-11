---
title: バージョン管理、ビジネス プロセス管理ソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- versioning, process management solutions
- process management solution tutorial, modifying
- process management solution tutorial, versioning
- processing, stages
- process management solution tutorial, processing stages
ms.assetid: 501b2162-821f-44e1-87c0-8628cc5bd9c3
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f3b030ed67745e37b9808d888a5f0df07e57bba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393753"
---
# <a name="versioning-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションのバージョン管理
ビジネス プロセス管理ソリューションでは、必要に応じてステージを置換できるように設計されています。 設計を簡単にスキーマのバージョン管理も提供します。  
  
 ビジネス プロセスをステージに分割する方法の詳細については、次を参照してください。 [、ビジネス プロセス管理ソリューションの一部の設計原則](../core/some-design-principles-in-the-business-process-management-solution.md)します。  
  
> [!NOTE]
>  ソリューションの要素は、メッセージ構造に大きく依存します。 メッセージの構造を変更するには、オーケストレーションに大幅な変更が必要です。  
  
 更新プログラムを処理するためにデプロイ済みのソリューションとスクリプトの記述に関するガイドラインのアセンブリの更新に関する一般的な説明は、次を参照してください。 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)します。  
  
## <a name="adding-replacing-or-removing-stages"></a>追加、置換、またはステージを削除します。  
 注文処理ステージ オーケストレーションは、2 種類のコードを含める: ビジネス プロセスと、ソリューションで動作できるように、インフラストラクチャを提供するコードを実装するコードです。 ステージのオーケストレーションの両方で**CableOrder1**と**CableOrder2**、ビジネス プロセス コード グループ図形内のラベルは「ビジネス処理します」。  
  
 新しいステージを作成する最も簡単な方法では、各ステージの 1 つをコピー、「ビジネス プロセス」グループ内のコードをコードに置き換えます、インフラストラクチャ コードをそのままです。  
  
> [!NOTE]
>  **CableOrder2**オーケストレーションが、「ビジネス プロセス」の 2 つのグループ、2 番目は Update History Send 図形です。 送信図形には、効率的な送信スコープの一部です。 (詳細についてを参照してください「の向上パフォーマンスで入れ子になったスコープ」 [OrderBroker オーケストレーションで処理](../core/processing-in-the-orderbroker-orchestration.md))。グループ図形はスコープ図形の一部を重ねることはできません、ため、2 番目のグループは、ビジネス プロセス コードの一部であることを示すラベルします。  
  
 シーケンスの番号に新しいオーケストレーションのフィルター式を設定する必要があります。 **OrderManager**ステージ番号は、いずれかで始めるし、各次のステージ (1, 2, 3...) を 1 ずつ増加を前提としています。 3 番目のステージをフィルター処理するには、次のフィルター式を設定します。  
  
 `(Microsoft.Samples.BizTalk.SouthridgeVidoe.Schemas.Stage == 3)`  
  
 ソリューションでは、BAM API を使用して、注文処理ステージを含む、ソリューション内のイベントを追跡します。 最初の段階、BAM アクティビティを開始します。最終ステージで終了します。 場合は、ソリューション内のハンドラー、例外が関連する BAM アクティビティを終了があります。 BAM は、効果的に再組み立てられますを監視するための継続的なビューに連続していない操作。  
  
## <a name="changing-configuration"></a>構成を変更します。  
 場合は、変更内容を拡大またはステージの数を減らす、エンタープライズ シングル サインオン (SSO) シークレット ストアに格納されている構成情報を変更する必要があります。  
  
 構成設定を変更するには、アプリケーションを展開していない場合**TotalStages** CreateSouthridgeVideoApplication.cmd スクリプト ファイル。 値は、デプロイ時に、スクリプトの実行時に変更されます。  
  
 アプリケーションが既にある場合は、sdk \common\ssoapplicationconfig フォルダでコマンド ライン ユーティリティ BTSScnSSOApplicationConfig を実行して値を変更できます。 ステージの合計数を 3 に設定するには、次のコマンドラインを使用します。  
  
 `BTSScnSSOApplicationConfig -set SouthRidgeVideo.CableOrder ConfigProperties TotalStages 3`  
  
 ソリューションが構成値をキャッシュするために、更新間隔が経過を有効にする新しい値になるまでを待つ必要があります。  
  
## <a name="versioning-schemas"></a>バージョン管理スキーマ  
 BizTalk は、それを含むアセンブリの最新のバージョンからのスキーマです。 これは、スキーマの新しいバージョンを作成する場合、完全にスキーマのすべての以前のバージョンが置き換えられますことを意味します。 これは、短期間のトランザクションの場合に有効です。 ただし、ビジネス プロセス管理ソリューションでのトランザクションは有効期間が長い: 完了 1 年間に注文かかる場合があります。  
  
 スキーマの複数のバージョンが使用される可能性を考慮して、ソリューションの各スキーマは名前空間にバージョン番号を含んでいます。 たとえば、注文スキーマの名前空間は次のようになっています。  
  
```  
http://Microsoft.Samples.BizTalk.SouthridgeVideo.Schemas.Order.v1  
```  
  
 名前空間は、スキーマとバージョン番号は含めることにも、スキーマに対して一意の名前空間を識別、ために、新しいスキーマは、以前のバージョンから個別になります。 したがって、古いスキーマを置き換えずに新しいスキーマを使用できます。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの開発](../core/developing-a-business-process-management-solution.md)