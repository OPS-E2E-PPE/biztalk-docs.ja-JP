---
title: 動的な変換を使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1e4aac7-242a-41b6-8df4-4881371f44d1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81476c0bdcdbcf3d5647dd7bc83b37a70d6e7557
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396442"
---
# <a name="using-dynamic-transformation"></a>動的な変換を使用します。
## <a name="overview"></a>概要  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]動的変換用の 3 つのメカニズムをサポートしています。  
  
- 動的変換エージェントがオーケストレーションとして実装されています  
  
- 動的変換コア Web サービスに含まれている Web サービス  
  
- ESB パイプライン コンポーネントによって実行される変換  
  
  このセクションでは、オーケストレーションとして実装されている変換エージェントについて説明します。 Web サービスの変換については、次を参照してください。 [BizTalk ESB Toolkit Web サービスを使用して](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md)します。 ESB ディスパッチャー パイプラインのコンポーネントについては、次を参照してください。[パイプライン サポート コンポーネントを使用して](../esb-toolkit/using-the-pipeline-support-components.md)します。  
  
## <a name="how-it-works"></a>しくみ  
 変換の配信エージェントはメッセージをサブスクライブするオーケストレーションは、場所、**名前**、現在の属性**ServiceInstance**旅行計画内の要素が**Microsoft.Practices.ESB.Services.Transform**します。 エージェントは、次の一連の操作を実行します。  
  
1.  型指定されていないメッセージ (System.Xml.XmlDocument) を受け取ります。  
  
2.  マップの名前を日程で静的な値として使用できる場合、エージェントは競合回避モジュールのマネージャーを使用して、マップの名前を解決しようとします。  
  
3.  適切なマップは、受信した送信元メッセージに適用されます。  
  
4.  BizTalk メッセージ ボックス データベースにマップの出力を発行します。  
  
## <a name="how-to-configure-dynamic-transformation"></a>動的な変換を構成する方法  
 旅行プラン デザイナーを使用して動的な変換を構成する方法の詳細については、次を参照してください。[旅行プランを使用してスケジュールの作成のデザイナー](../esb-toolkit/creating-itineraries-using-itinerary-designer.md)します。  
  
## <a name="dynamic-transformation-errors"></a>動的変換エラー  
 動的変換メカニズムは作成し、次の場合に、ESB エラー メッセージを発行します。  
  
- 競合回避モジュール コンポーネントは、適用に割り当てられている特定できません。  
  
- 指定したマップは利用できません (たとえば、指定した、正しくないマップ型または BizTalk Server 2009 でまだ展開されているマップ) します。  
  
- マッピング中にエラーが発生した (たとえば、ソース ドキュメントは、正しいソースの種類または外部アセンブリ内のユーザー定義関数が BizTalk に配置されているマップの参照)。  
  
- マップの種類のジャストイン タイム (JIT) の解決中に例外が発生します。  
  
- 出力メッセージのサブスクライバーが存在しません。  
  
- すべてのシステム例外が発生します。  
  
  例外メッセージを設定して、例外に対応するためのハンドラーを作成するために使用するコンテキスト情報を提供する、開発者の役目です。 データの一部が自動的に使用して、ターゲット ハンドラーが指定されたか使用できない場合は、ジェネリック ハンドラーを例外メッセージを選択します。 動的な変換の例外の処理の詳細については、次を参照してください。 [ESB 例外管理を使用して](../esb-toolkit/using-esb-exception-management.md)します。