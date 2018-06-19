---
title: TPE を使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, about Tracking Profile Editor
- tracking profiles, prerequisites
ms.assetid: ebe9a5da-66ec-482d-8aac-892a829ca996
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0fa826ce68042336c2b6e4fb006ecb278a3f981
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288074"
---
# <a name="using-the-tpe"></a>TPE の使用
オーケストレーションとプロパティを BAM アクティビティ定義にマップするには、追跡プロファイル エディター (TPE) を使用します。  
  
 TPE のユーザーは、マイルストーンやコンテキスト データ ("表示希望リスト" と呼ばれることもある) などの BAM アクティビティの項目間にマップ (つまり追跡プロファイル) を作成し、これらの項目の BizTalk ソリューション ソースを作成します。  
  
 **追跡プロファイルの作成**  
  
 たとえば、「PO を受信しました」というマイルス トーンを含む BAM アクティビティ 開発者は、他の BizTalk Server 開発ツールでプロセスを作成することから、実際のプロセスが注文書が経由は処理を開始するメッセージング ポートが含まれています。 開発者は、"PO 受領済み" というアクティビティ マイルストーンが、ソリューションのポートの "PortEndTime" という BizTalk メッセージング プロパティに適切に関連付けられていると判断しました。 開発者は、追跡プロファイルを完成するために、アクティビティを読み込み、イベント ソースを選択し、イベント ソースの適切な項目をアクティビティ ツリー定義の対応するノード上にドラッグ アンド ドロップして、必要なマッピングを行います。  
  
 **プロファイルを作成するための前提条件**  
  
 追跡プロファイルを作成するには、次の 2 つの前提条件が満たされている必要があります。  
  
1.  BAM アクティビティが全体的な監視モデルの一部としてビジネス アナリストによって定義され、システム管理者によって展開されている。  
  
2.  BizTalk ソリューション (オーケストレーション、スキーマ、マップ、パイプラインなど) がターゲット環境に正しく展開されている。  
  
 インストール後にデータベースから取得されるデータは TPE に挿入されないので、これらの前提条件が必要となります。  
  
 **カスタマイズされた BAM ソリューションのプロファイルを作成します。**  
  
 追跡プロファイルを使用できるのは、インターセプターを持つランタイムに関してのみです。 BAM API を使用したカスタム コードから構成される BAM ソリューションの場合は、関連付けられている BAM ランタイム インターセプターがありません。したがって、BAM にデータを送信する方法は、次の 2 つしかありません。  
  
-   BAM API を使用して直接送信する。 開発者は、BAM API を使用して、BAM インフラストラクチャにイベント データを明示的に送信できます。 詳細については、BAM Api を使用して、次を参照してください。[イベント ストリームを使用した BAM アクティビティを実装する](../core/implementing-bam-activities-with-event-streams.md)です。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロパティを介して間接的に送信する。 カスタム アセンブリを呼び出す際に、関連する傍受テクノロジ (カスタム パイプラインなど) や式/アクション図形が含まれているランタイム コンテキストの内部でカスタム コードを実行している場合は、上記の BAM API か、従来のデータ昇格技法を使用できます。 プロパティを昇格させて TPE にアクセスできるようにします。これにより、適切なコンテキスト プロパティを使用して、イベント データと BAM アクティビティ項目との関連付けを TPE 内に作成できるようになります。 プロパティの昇格の詳細については、次を参照してください。[プロパティの昇格](../core/promoting-properties.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [追跡プロファイルを作成します。](../core/creating-tracking-profiles.md)  
  
-   [孤立した追跡プロファイルを削除する方法](../core/how-to-remove-orphaned-tracking-profiles.md)  
  
-   [複数の Continuation を使用します。](../core/using-multiple-continuations.md)