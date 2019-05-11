---
title: パイプライン ステージ |Microsoft Docs
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
ms.openlocfilehash: c3e24d6660e56bfbd44391b092152735f67fbb23
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395784"
---
# <a name="pipeline-stages"></a>パイプライン ステージ
このトピックで説明、**実行モード**プロパティとステージ関係します。  
  
## <a name="execution-mode-property"></a>実行モードのプロパティ  
 パイプラインの実行中には、パイプライン ステージは、メッセージの形式を認識する最初のコンポーネントのみまたはすべてのコンポーネントを実行できます。 実行パターンを決定するプロパティが**実行モード**します。  
  
> [!NOTE]
>  このプロパティは読み取り専用で、ステージ、パイプライン テンプレートに含まれるが、重要な概念は、そのしくみを理解します。  
  
 ときに、**実行モード**プロパティに設定されて**すべて**ステージ内のすべてのコンポーネントが構成されている順序で実行されます。 このモードでは、論理タスクを完了するいくつかのコンポーネントを実行します。 この場合、このパイプライン ステージにメッセージを処理中にエラーが発生したコンポーネントと、実行時エラーが発生します。  
  
 パイプラインを使用して、いくつかの形式でメッセージを受信するときに、**実行モード**プロパティに設定されて**FirstMatch**します。 このモードでは、メッセージを認識する最初のコンポーネントのみが実行されます。 ステージのコンポーネントがメッセージを認識しなかった場合を実行時エラーが発生します。  
  
 各ステージがあることができます独自ことに注意してください。**実行モード**パイプライン内の設定では、異なるステージは異なる実行モードであることができます。  
  
> [!NOTE]
>  このリリースの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、すべての段階、送信パイプラインおよび受信パイプラインの逆アセンブルを除くすべての段階でなければ、**実行モード**プロパティに設定**すべて**します。 値、**実行モード**逆アセンブル ステージでプロパティに設定されて**FirstMatch**します。 変更することはできません、**実行モード**ステージのプロパティ。  
  
#### <a name="to-read-pipeline-stage-properties"></a>パイプライン ステージのプロパティを読み取る  
  
1.  パイプライン デザイナーでステージの図形をクリックします。  
  
2.  プロパティ ウィンドウでの**全般** セクションで、次のプロパティの読み取り。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|ステージの名前を示します。|  
    |**[実行モード]**|ステージの実行パターンを示します。<br /><br /> 有効な値:**すべて**または**FirstMatch**|  
    |**コンポーネントの最小数**|ステージに追加できるパイプライン コンポーネントの最小数を示します。|  
    |**コンポーネントの最大数**|ステージに追加できるパイプライン コンポーネントの最大数を示します。|  
    |**StageID**|ステージの一意の識別子を示します。|  
  
## <a name="stage-affinity"></a>ステージ関係  
 パイプライン コンポーネントがあるステージ関係を特定のステージまたはステージ、パイプライン内で使用するために作成されたことを意味します。  
  
 COM ベースのパイプライン コンポーネントは、実装カテゴリとしてステージ ID を使用して自身を登録することにより、ステージ関係を express にします。NET ベースのパイプライン コンポーネントを使用して、ステージ関係を指定する、 **ComponentCategory**クラス属性。 コンポーネント自体を 1 つ以上のステージに関連付けることは、コンポーネントが 1 つ以上の実装カテゴリを持つことができますまたは**ComponentCategory**属性。  
  
 次の表は、使用可能なコンポーネントのカテゴリとその関連付けられたステージを示します。  
  
|コンポーネント カテゴリ|ステージのコンポーネントを配置できる場所|説明|  
|------------------------|-----------------------------------------|-----------------|  
|CATID_Decoder {9d0e4103-4cce-4536-83fa-4a5040674ad6}|デコード|すべてのデコード コンポーネントは、このカテゴリを実装する必要があります。|  
|CATID_DisassemblingParser {9d0e4105-4cce-4536-83fa-4a5040674ad6}|逆アセンブルします。|すべての逆アセンブル コンポーネントおよび解析コンポーネントは、このカテゴリを実装する必要があります。|  
|CATID_Validate {9d0e410d-4cce-4536-83fa-4a5040674ad6}|[検証]|検証コンポーネントは、このカテゴリを実装する必要があります。|  
|CATID_PartyResolver {9d0e410e-4cce-4536-83fa-4a5040674ad6}|パーティの解決|パーティの解決コンポーネントに使用する段階です。|  
|CATID_Encoder {9d0e4108-4cce-4536-83fa-4a5040674ad6}|エンコード|すべてのエンコード コンポーネントは、このカテゴリを実装する必要があります。|  
|CATID_AssemblingSerializer {9d0e4107-4cce-4536-83fa-4a5040674ad6}|シリアル化します。|すべてのシリアル化およびアセンブラー コンポーネントは、このカテゴリを実装する必要があります。|  
|CATID_Any {9d0e4101-4cce-4536-83fa-4a5040674ad6}|これらのステージのいずれか|パイプライン コンポーネントは、このカテゴリを実装する場合は、コンポーネントをパイプラインのすべてのステージに配置できることを意味します。|  
  
## <a name="see-also"></a>参照  
 [パイプライン デザイナーを使用してパイプラインを作成します。](../core/creating-pipelines-using-pipeline-designer.md)   
 [パイプライン、ステージ、およびコンポーネントについて](../core/about-pipelines-stages-and-components.md)