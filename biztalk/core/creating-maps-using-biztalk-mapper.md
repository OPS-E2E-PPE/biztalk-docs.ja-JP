---
title: BizTalk マッパーを使用してマップを作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, maps
- maps, creating
- orchestrations, maps
- translations [maps]
- maps, about maps
- transformations [maps]
- maps
ms.assetid: 265e61d8-8cff-44c9-a717-8e895cb4b9bf
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b295fbe516c6a30f7244dbfe0cbec83480ec0bba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389921"
---
# <a name="creating-maps-using-biztalk-mapper"></a>BizTalk マッパーでのマップの作成
BizTalk マッパーは、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 環境内で動作するツールです。 BizTalk マッパーを使用すると、XML メッセージの変換に必要なマップを作成および編集できます。 マップは、オーケストレーション (次の図を参照) に使用されるほか、受信ポートで受け取ったメッセージを処理し、変換を適用してから、送信ポートを介して送信するという目的にも使用されます。  
  
 ![マップとビジネス プロセス ダイアグラム。](../core/media/ebiz-dev-busprcsg.gif "ebiz_dev_busprcsg")  
ビジネス プロセスのマップ  
  
 マップを使用して、メッセージを変換 (トランスレートまたはトランスフォーム) できます。 トランスレートは、フラット ファイルから XML ファイルへの変換など、ある形式から別の形式にメッセージを変換する処理です。 トランスフォームは、あるメッセージから情報を取得し、別のメッセージにその情報を挿入する処理です。 たとえば、注文書から送付先住所および請求先住所を取得し、請求書に挿入する場合などです。  
  
 BizTalk マッパーでは、独自のグラフィカル システムに基づいたアイコンやリンクを使用して、インスタンス メッセージを出力するための入力インスタンス メッセージの変換 (トランスレートまたはトランスフォーム) を表します。 マッパーで使用されるスキーマのグラフィカル表示は、BizTalk エディターと同じものです。 BizTalk マッパーは、XSLT (Extensible Stylesheet Language Transformations) スタイルシートとしてマップを保存します。  
  
> [!NOTE]
>  BizTalk マッパーは XSLT 1.0 をサポートします。 XSLT 2.0 の使用は、BizTalk マッパーではサポートされていません。  
  
 スキーマの作成方法の詳細については、次を参照してください。 [BizTalk エディターを使用してスキーマを作成する](../core/creating-schemas-using-biztalk-editor.md)です。 オーケストレーション内でマップを使用する方法の詳細については、次を参照してください。[オーケストレーション デザイナーを使用してオーケストレーションを作成する](../core/creating-orchestrations-using-orchestration-designer.md)です。  
  
> [!NOTE]
>  マップのパフォーマンスは、マップの複雑さ (Functoid の数と種類)、入力/出力スキーマのサイズ、入力メッセージのサイズ、およびハードウェアに依存します。  
  
 BizTalk マッパーのキーボード ショートカットの使用方法の詳細については、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [マップを作成する計画](../core/planning-to-create-maps.md)  
  
-   [マップの概要](../core/about-maps.md)  
  
-   [BizTalk マッパーの使用](../core/using-biztalk-mapper.md)  
  
-   [マップを作成します。](../core/creating-maps.md)  
  
-   [コンパイルして、マップのテスト](../core/compiling-and-testing-maps.md)  
  
-   [マップのトラブルシューティング](../core/troubleshooting-maps.md)