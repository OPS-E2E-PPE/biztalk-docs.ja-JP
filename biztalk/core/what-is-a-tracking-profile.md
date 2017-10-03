---
title: "追跡プロファイルについて | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracking profiles, about tracking profiles
- tracking profiles, Tracking Profile Editor
- Tracking Profile Editor, tracking profiles
- tracking profiles
ms.assetid: b579bdc4-7c69-4fa0-bbc1-f98170c13d4f
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da032fb6063d81cedca9f21899c5e2bbe6eca947
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-a-tracking-profile"></a>追跡プロファイルについて
プロファイルとは、ビジネス プロセスを定義する一連の特性です。 追跡プロファイルには、アクティビティからオーケストレーションやポートへの特性のマッピングが含まれています。 追跡プロファイルは、ファイル名拡張子に .btt の付いたファイルです。  
  
## <a name="using-tracking-profiles-in-the-tpe"></a>TPE での追跡プロファイルの使用  
 TPE のユーザーは、BAM アクティビティ内の項目とその項目に対応する BizTalk Server ソリューションとの間に、マップ (追跡プロファイル) を作成します。 BAM アクティビティは、マイルストーンやコンテキスト データ ("表示希望リスト") で構成され、追跡プロファイルが従うビジネスの作業単位を定義します。 アクティビティに関する詳細については、次を参照してください。[イベント ストリームを使用した BAM アクティビティを実装する](../core/implementing-bam-activities-with-event-streams.md)です。  
  
 TPE を使用して追跡プロファイルを作成する場合は、次のオブジェクトを操作します。  
  
-   BAM アクティビティ  
  
-   展開済みアセンブリの BizTalk オーケストレーション  
  
-   受信ポートと送信ポート  
  
-   展開済みアセンブリのメッセージ スキーマ  
  
-   コンテキスト プロパティ  
  
-   BAM プライマリ インポート データベース  
  
-   BizTalk 管理データベース  
  
-   BizTalk 追跡データベース  
  
 オーケストレーションからデータ抽出を定義するには、メッセージ スキーマ、オーケストレーション図形、およびコンテキスト プロパティから、ビジネス マイルストーン (イベント) およびデータ項目フォルダーに項目をドロップします。  
  
 たとえば、ある BAM アクティビティに "PO 受領済み" というマイルストーンが含まれていて、処理を開始するために注文書が経由するメッセージング ポートがあるとします。 この場合、開発者は `PO Received` マイルストーンを、ソリューションのポートの `PortEndTime` という BizTalk メッセージング プロパティに関連付けることができます。 つまり、受信ポートがそのアクションを完了して、`PortEndTime` プロパティを設定した結果として、PO が正しく受信されることを意味します。 開発者は、このマッピングやその他のマッピングを行い、追跡プロファイルを完成させます。 アクティビティ内の項目はすべて、BizTalk Server ソースがあればマップされます。データまたはイベントのソースが、BizTalk Server の実行環境外のプロセスから取得するものである場合は、マップされずに API 呼び出しによって直接設定されます。  
  
 TPE 内の各ペインやビューにはそれぞれ固有の機能がありますが、すべてのビューおよびフォルダーに共通して、情報の検索や操作に役立つナビゲーション機能もあります。  
  
## <a name="who-uses-tracking-profiles-and-the-tpe"></a>追跡プロファイルと TPE の使用者について  
 企業の統合開発に参加しているユーザーは、追跡プロファイルと TPE を使用して、BizTalk Server イベント ソースを BAM ターゲット アクティビティにマップします。 展開時に、完成した .btt ファイルを IT 実装に渡します。  
  
 IT 実装を担当するユーザーは、通常、コマンド ライン ツール (BTTDeploy) を使用して追跡プロファイルを適用します。 また、直接 TPE を使用して追跡プロファイルを適用することもできます。  
  
 IT 運用を担当するユーザーは、特に、ビジネス要件の変更を受け、(バックアップや復元など、必要なデータベース操作を含めて) スケジュールに基づいて追跡プロファイルを定期的に更新する役割を担う場合があります。  
  
## <a name="see-also"></a>参照  
 [追跡プロファイル エディター](../core/tracking-profile-editor.md)