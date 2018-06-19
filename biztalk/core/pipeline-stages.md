---
title: パイプライン ステージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, properties
- CATID_AssemblingSerializer component category
- CATID_Encoder component category
- pipelines, stages
- CATID_DisassemblingParser component category
- CATID_Validate component category
- ComponentCategory class attribute
- CATID_Decoder component category
- CATID_Any component category
- CATID_PartyResolver component category
- Execution Mode property
ms.assetid: ac50c48c-6ed5-4322-95cc-af55df6bcd1c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aeb675f39cb39ade4230e6e39f798e95115aaf78
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265506"
---
# <a name="pipeline-stages"></a>パイプラインのステージ
このトピックの内容について説明します、**実行モード**プロパティとステージ関係します。  
  
## <a name="execution-mode-property"></a>"実行モード" プロパティ  
 パイプライン ステージでは、パイプラインの実行中、メッセージの形式を識別する最初のコンポーネントだけが実行される場合と、すべてのコンポーネントが実行される場合とがあります。 実行パターンを決定するプロパティは**実行モード**です。  
  
> [!NOTE]
>  このプロパティは、パイプライン テンプレートに追加されたステージの読み取り専用プロパティとして存在しますが、その動作を理解することは重要です。  
  
 ときに、**実行モード**プロパティに設定されている**すべて**ステージ内のすべてのコンポーネントが構成されている順序で実行されます。 このモードは、論理タスクを完了するために複数のコンポーネントを実行します。 この場合、このパイプライン ステージに送信されたメッセージを処理しているときに、いずれかのコンポーネントでエラーが発生すると、実行時エラーが発生します。  
  
 パイプラインを使用して、いくつかの形式でメッセージを受信するときに、**実行モード**プロパティに設定されている**FirstMatch**です。 このモードでは、メッセージを認識した最初のコンポーネントだけが実行されます。 ステージ内のいずれのコンポーネントもメッセージを認識しなかった場合、実行時エラーが発生します。  
  
 各ステージがあることができます独自ことに注意してください**実行モード**パイプライン内での設定では、大きく異なるステージが別の実行モードを持つことができます。  
  
> [!NOTE]
>  このリリースで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、すべての段階、送信パイプラインおよび受信パイプラインの逆アセンブルを除くすべてのステージは、値を持つ、**実行モード**プロパティに設定**すべて**です。 値、**実行モード**逆アセンブル ステージでプロパティに設定されて**FirstMatch**です。 変更することはできません、**実行モード**ステージのプロパティです。  
  
#### <a name="to-read-pipeline-stage-properties"></a>パイプライン ステージのプロパティを確認するには  
  
1.  パイプライン デザイナーでステージの図形をクリックします。  
  
2.  プロパティ ウィンドウでの**全般** セクションで、次のプロパティの読み取り。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|ステージの名前を示します。|  
    |**[実行モード]**|ステージの実行パターンを示します。<br /><br /> 有効な値:**すべて**または**FirstMatch**|  
    |**コンポーネントの最小数**|ステージに追加することのできるパイプライン コンポーネントの最小数を示します。|  
    |**コンポーネントの最大数**|ステージに追加することのできるパイプライン コンポーネントの最大数を示します。|  
    |**StageID**|ステージの一意の識別子です。|  
  
## <a name="stage-affinity"></a>ステージ関係  
 パイプライン コンポーネントは、そのコンポーネントがパイプラインの特定のステージ (1 つまたは複数) 内で使用するために作成されたことを意味するステージ関係を持ちます。  
  
 COM ベースのパイプライン コンポーネントがステージ ID を使用して、実装カテゴリとして自分自身を登録することにより、ステージ関係を表すときにします。NET ベースのパイプライン コンポーネントを使用して、ステージ関係を指定する、 **ComponentCategory**クラスの属性です。 あること、コンポーネント自体を 2 つ以上のステージに関連付けることに注意してください: コンポーネントが 1 つ以上の実装カテゴリを持つことができますか**ComponentCategory**属性。  
  
 次の表は、コンポーネントのカテゴリと、それぞれに関連付けられたステージを示しています。  
  
|コンポーネント カテゴリ|コンポーネントを配置可能なステージ|Description|  
|------------------------|-----------------------------------------|-----------------|  
|CATID_Decoder {9d0e4103-4cce-4536-83fa-4a5040674ad6}|デコード|すべてのデコード コンポーネントはこのカテゴリを実装する必要があります。|  
|CATID_DisassemblingParser {9d0e4105-4cce-4536-83fa-4a5040674ad6}|逆アセンブル|すべての逆アセンブル コンポーネントおよび解析コンポーネントは、このカテゴリを実装する必要があります。|  
|CATID_Validate {9d0e410d-4cce-4536-83fa-4a5040674ad6}|[検証]|すべての検証コンポーネントはこのカテゴリを実装する必要があります。|  
|CATID_PartyResolver {9d0e410e-4cce-4536-83fa-4a5040674ad6}|パーティの解決|パーティの解決コンポーネントに使用されるステージです。|  
|CATID_Encoder {9d0e4108-4cce-4536-83fa-4a5040674ad6}|エンコード|すべてのエンコード コンポーネントはこのカテゴリを実装する必要があります。|  
|CATID_AssemblingSerializer {9d0e4107-4cce-4536-83fa-4a5040674ad6}|シリアル化します。|すべてのシリアル化コンポーネントおよびアセンブル コンポーネントは、このカテゴリを実装する必要があります。|  
|CATID_Any {9d0e4101-4cce-4536-83fa-4a5040674ad6}|上記の全ステージ|このカテゴリを実装するパイプライン コンポーネントは、任意のパイプライン ステージに配置できます。|  
  
## <a name="see-also"></a>参照  
 [パイプライン デザイナーを使用してパイプラインを作成します。](../core/creating-pipelines-using-pipeline-designer.md)   
 [パイプライン、ステージ、およびコンポーネントについて](../core/about-pipelines-stages-and-components.md)