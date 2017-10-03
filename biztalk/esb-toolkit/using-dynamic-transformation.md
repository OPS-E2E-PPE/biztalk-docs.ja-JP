---
title: "動的な変換を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1e4aac7-242a-41b6-8df4-4881371f44d1
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d7f6bc57d009e558188950d9bcb0387f808f835
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-dynamic-transformation"></a>動的な変換を使用します。
## <a name="overview"></a>概要  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]動的変換の 3 つのメカニズムをサポートしています。  
  
-   オーケストレーションとして実装されている動的変換エージェント  
  
-   コア Web サービスに含まれる Web サービスの動的変換  
  
-   ESB パイプライン コンポーネントによって実行される変換  
  
 このセクションでは、オーケストレーションとして実装されている変換エージェントについて説明します。 Web サービスの変換については、次を参照してください。 [BizTalk ESB Toolkit の Web サービスを使用して](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md)です。 ESB ディスパッチャー パイプライン コンポーネントについては、次を参照してください。[サポートのパイプライン コンポーネントを使用して](../esb-toolkit/using-the-pipeline-support-components.md)です。  
  
## <a name="how-it-works"></a>しくみ  
 変換配信エージェントはメッセージをサブスクライブするオーケストレーションを**名前**、現在の属性**ServiceInstance**旅行計画内の要素は**Microsoft.Practices.ESB.Services.Transform**です。 エージェントでは、次の操作手順を実行します。  
  
1.  型指定されていないメッセージ (system.xml.xmldocument など) を受け取ります。  
  
2.  マップの名前は、旅行計画で静的な値として使用できますが、エージェントは競合回避モジュールのマネージャーを使用して、マップの名前を解決しようとします。  
  
3.  入力方向の送信元のメッセージを適切なマップを適用します。  
  
4.  マップの出力に、BizTalk メッセージ ボックス データベースに発行します。  
  
## <a name="how-to-configure-dynamic-transformation"></a>動的な変換を構成する方法  
 行程デザイナーを使用して動的な変換を構成する方法の詳細については、次を参照してください。[旅程を使用して日程作成のデザイナー](../esb-toolkit/creating-itineraries-using-itinerary-designer.md)です。  
  
## <a name="dynamic-transformation-errors"></a>動的な変換エラー  
 動的な変換のメカニズムが作成され、次の場合、ESB フォールト メッセージを発行します。  
  
-   競合回避モジュール コンポーネントは、適用するマップを判断できません。  
  
-   指定したマップは使用できません (たとえば、指定した、正しくないマップ型、または BizTalk Server 2009 ではまだ展開されているマップ) します。  
  
-   マッピング中にエラーが発生した (たとえば、ソース ドキュメントは、正しいソースの種類または外部アセンブリ内のユーザー定義関数は、BizTalk に展開されていないマップの参照の)。  
  
-   例外は、マップの種類の・ イン タイム (JIT) の解決時に発生します。  
  
-   出力メッセージのサブスクライバーが存在しません。  
  
-   すべてのシステム例外が発生します。  
  
 例外メッセージを作成し、例外に反応するためのハンドラーを作成するために使用するコンテキスト情報を提供する、開発者の責任です。 データの一部が自動的に使用して、ジェネリック ハンドラーが指定されているか使用可能なターゲット ハンドラーがない場合、例外メッセージを取得します。 動的な変換の例外の処理の詳細については、次を参照してください。 [ESB 例外管理を使用して](../esb-toolkit/using-esb-exception-management.md)です。