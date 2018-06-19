---
title: Excel でビジネス アクティビティとビューの定義 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], creating business activities
- monitoring business activities [BAM], creating business activities
ms.assetid: 000532f0-cb9a-40ac-a6c5-a8bd4e49f8d0
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91b9d3b213a6a6429759c0bb0d826798afa36da3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239682"
---
# <a name="defining-business-activities-and-views-in-excel"></a>Excel でのビジネス アクティビティとビジネス ビューの定義
BAM ソリューションを作成する場合は、まず関連データの種類とそのデータを解釈する方法を指定します。 これには、Excel 用の BAM アドインを使用します。 このアドインを使用すると、ビジネス アクティビティを定義して、関連データの希望リストを定義できます。 また、データを解釈する方法と、さまざまなカテゴリのビジネス ユーザーにデータを公開する方法を定義できます。  
  
 BAM アドインでは、集計も定義できます。  
  
 アクティビティ項目の名前の変更も可能です。たとえば、ユーザーにとって一般的な用語と、アクティビティの対応するデータ項目の名前が一致しない場合に名前を変更できます。 たとえば、表示が別の言語になっている場合が挙げられます。  
  
 アクティビティの定義が完了すると、必要なグラフおよびその他のプレゼンテーション手段の定義に使用できるランダムなプレビュー データが Excel で作成されます。 データのプレビューの詳細については、次を参照してください。[ピボット テーブルを使用する方法](../core/how-to-use-the-pivottable.md)です。  
  
 完成したアクティビティ定義では、ビジネス プロセスの実行時に収集する必要があるデータ ポイントとイベントが定義されています。 BAM アドインは、さまざまな方法で入手できます。  
  
 中に BAM アドイン XLA をインストールすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールします。 詳細については、次を参照してください[BizTalk Server 2013 および 2013 R2 のインストールの概要。](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)  
  
 Bam の展開。XLA ファイルは、次の場所のいずれかでインストールされます。  
  
-   コンピューターで、Microsoft Office がインストールされていない場合、BAM.xla が BizTalk Server 20 \Program Files\Microsoft にインストールされている*xx*\ExcelDir\ フォルダーです。  
  
-   Microsoft Office がインストールされている場合、BAM.xla は \Program Files\Microsoft Office\OFFICE にインストール*xx*\Library\ フォルダーです。  
  
 使用するコンピューターに、別のコンピューターの共有フォルダーから BAM.xla をコピーすることもできます。 コピーしたら、その場所で XLA を選択して XLA を登録できます。  
  
 Excel メニュー バーで BAM アドインを有効にする をクリックして、**ファイル** メニューのをクリックし、**オプション**、順にクリック**アドイン**です。選択**ビジネス アクティビティ監視**をクリックし、**移動**、Ad アドイン ウィンドウに横にチェック ボックスをオン**ビジネス アクティビティ監視**をクリックして**OK**です。  
  
> [!NOTE]
>  BAM アドインの使用中、Excel では同じプロセスに 2 つのインスタンスを読み込むことはできません。  アドインの使用中に、同じプロセスへの複数インスタンスの読み込みが発生するのは次のような場合です。  
>   
>  BAM アドインを有効にした状態で Excel ワークシートを開き、さらに別の Excel ワークシートをダブルクリックした場合。この場合、Excel によってダブルクリックしたワークシートが実行中のインスタンスに読み込まれます。  
>   
>  BAM アドインを有効にした状態で Excel ワークシートを開き、さらに [ファイル] メニューの [開く] を選択して他の Excel ワークシートを読み込んだ場合。  
  
 このような状況では、アドインを適切に使用できません。 BAM アドインを有効にした状態で複数の Excel ワークシートを開くには、新しい Excel のウィンドウを開き、その Excel インスタンスにワークシートを読み込む必要があります。  
  
> [!NOTE]
>  BAM.xla を Excel で使用するときにエラーが発生、「このブックを失って、VBA プロジェクト、ActiveX コントロールおよびその他のプログラミング関連の機能です」 エラーの詳細については、次を参照してください。[トラブルシューティング BAM](../core/troubleshooting-bam.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ビジネス アクティビティを定義する方法](../core/how-to-define-a-business-activity.md)  
  
-   [BAM ビューを定義します。](../core/defining-a-bam-view.md)  
  
## <a name="see-also"></a>参照  
 [BAM によるビジネス アクティビティの監視](../core/monitoring-business-activities-with-bam.md)