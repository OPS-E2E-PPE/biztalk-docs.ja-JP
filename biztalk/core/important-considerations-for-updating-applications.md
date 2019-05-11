---
title: アプリケーションを更新するための重要な考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- updating, applications
- applications, planning
- applications, updating
- planning, applications
- planning, updating
- updating, planning
ms.assetid: e7690bdf-943d-4bb6-b8cd-a6841b722d40
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39b3bdd5d939edd1fa1d930d5711f8bac8a8f71c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382590"
---
# <a name="important-considerations-for-updating-applications"></a>アプリケーションを更新するための重要な考慮事項
特に 1 つ、実稼働環境で実行されているアプリケーションを更新する前に考慮すべき重要な問題を次に示します。  
  
## <a name="general-considerations"></a>全般的な考慮事項  
  
-   パーティおよびルールは、他のアプリケーションに悪影響を及ぼすその他のパーティおよびルールを追加するため、グループのスコープで表示されます。  
  
-   別のアイテムが依存するアイテムの展開を解除する場合、依存するアイテムでなければなりませんデプロイ最初。  
  
    > [!NOTE]
    >  BizTalk Server 管理コンソールは警告を表示して、間違った順序でアイテムの展開解除されないようにします。  
  
-   既存のアプリケーションでの BizTalk アセンブリが更新された場合は、変更を反映するためのホスト インスタンスを再起動する必要があります。 ホスト インスタンスを再起動すると、ホスト インスタンスで実行されているその他のすべてのアプリケーションが停止します。  
  
-   すべてのホスト インスタンスが、アプリケーションを展開するときに再起動されます (これは強く、操作は実行しないお勧めします)、運用環境にアプリケーションを配置する Visual Studio を使用すると、プロジェクトのプロパティで、ホスト インスタンスを再起動オプションが True に設定、このアプリケーションに関連付けられていないものも含めています。 ローカル コンピューター上の任意のホスト インスタンスで実行されているその他のすべてのアプリケーションを停止します。  
  
-   BizTalk アプリケーションとして展開される BizTalk Server アセンブリ (オーケストレーション、スキーマ、またはマップを含む) を更新する場合は、次のいずれかの操作を行います。  
  
    -   サイド バイ サイド展開を実行します。 バージョンをインクリメントして通常適切に新しいアセンブリを変更できます。 これにより、両方の完全修飾アセンブリ名があるアセンブリ。 詳細については、次を参照してください。[実行のサイド既存のバージョンへのアプリケーションの新しいバージョンをデプロイする方法](../core/deploy-new-application-version-to-run-side-by-side-with-existing-version.md)します。  
  
    -   新しいアセンブリでは、既存の BizTalk Server アセンブリを置き換えます。 古いアセンブリを読み込む可能性、GAC 内の古いアセンブリを交換し、ホスト インスタンスを再起動するすべてのホスト インスタンスを停止する必要があります。  
  
-   既存のアプリケーションを置換するまったく新しいアプリケーションを展開する場合は、他のアプリケーションと交換するアプリケーションの間の参照を修正する必要があります。  
  
## <a name="considerations-for-updating-schemas"></a>スキーマの更新に関する注意点  
  
-   にアセンブリを BizTalk グループ内の既存のスキーマと同じメッセージ型を持つ新しいスキーマを含むアプリケーションを追加する場合は、スキーマの解決はパイプラインで発生すると最高のバージョン番号を持つスキーマが使用されます。 さらに、1 つのメッセージの種類は、1 つ以上の .NET 型を参照している場合、このあいまいさは、パイプラインの実行エラーを生じる。 これは、メッセージの種類、ターゲットの名前空間、およびインスタンスのルート名がスキーマの検索に使用されるためです。 これは、パイプラインで、スキーマ、新しいスキーマと同じメッセージの種類を使用する任意のアプリケーションで発生します。 スキーマの解決の詳細については、次を参照してください。[スキーマの解決パイプライン コンポーネントで](../core/schema-resolution-in-pipeline-components.md)します。  
  
-   スキーマを更新するときに、スキーマに依存するすべてのオーケストレーションとスキーマを参照します (または新しいマップを作成する) のマップを更新することも必要があります。  
  
-   スキーマのバージョンをインクリメントする場合は、すべてのパイプライン インスタンスとそれを使用するパイプライン コンポーネントのスキーマへの参照を更新する必要があります。  
  
-   スキーマを展開解除と、使用可能なアクティブになる場合のスキーマの以前のバージョンです。  
  
## <a name="considerations-for-updating-policies"></a>ポリシーの更新に関する注意点  
  
-   展開された状態にあるポリシーの最新バージョンは、BizTalk Server ランタイムによって使用されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)