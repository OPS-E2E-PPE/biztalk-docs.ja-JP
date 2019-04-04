---
title: パイプライン デザイナーを使用してパイプラインを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, processing messages
- pipelines, Pipeline Designer
- Pipeline Designer, about Pipeline Designer
ms.assetid: 858302d8-a912-4199-95e5-4322db789b4e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62e182440522e82f7ae6eaeaf52234161bee7483
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998611"
---
# <a name="creating-pipelines-using-pipeline-designer"></a>パイプライン デザイナーを使用してパイプラインを作成します。
Microsoft BizTalk Server は、主に XML ドキュメント形式を処理します。 BizTalk Server の機能を最大限に活用してメッセージを処理するには、多くの場合、ネイティブ形式から XML 表現へ変換する必要があります。 BizTalk Server パイプラインでは、受信メッセージおよび送信メッセージに対して、データの暗号化や復号化、プロパティの昇格などのデータ自身に対する操作だけでなく、ネイティブ形式から XML 表現への変換といったメッセージ変換も行います。 このセクションでは、パイプラインおよびパイプライン デザイナーに関する概要とタスク固有の情報について説明します。  
  
 パイプラインは、アダプターで受信したメッセージをサーバーで処理するための準備をしたり、サーバーで処理したメッセージを送信するための準備をする役割を担っています。  
  
 通常、パイプラインは、次の処理を行います。  
  
- さまざまな形式から XML 形式へのデータの正規化  
  
- XML 形式からさまざまな形式へのデータ変換  
  
- プロパティの昇格および降格  
  
- ドキュメントの逆アセンブリおよびアセンブリ  
  
- ドキュメントのデコードおよびエンコード  
  
- ドキュメントの復号化および暗号化  
  
- ドキュメントの署名およびデジタル署名の確認  
  
  パイプラインでのメッセージ処理を含むワークフローを次に示します。  
  
  ![メッセージを処理するためのワークフローのダイアグラム。](../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")  
  メッセージ処理ワークフロー  
  
  図に示すように、メッセージは、アダプターから受信パイプラインに渡されます。この受信パイプラインで、メッセージが XML に変換されます。 この後、メッセージはオーケストレーションで使用可能になります。また、メッセージを送信パイプラインに渡してから、送信アダプターに渡すこともできます。  
  
  パイプライン デザイナーのキーボード ショートカットの使用方法の詳細については、[パイプライン デザイナーのキーボード ショートカット](../core/pipeline-designer-keyboard-shortcuts.md)を参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [パイプライン、ステージ、およびコンポーネントについて](../core/about-pipelines-stages-and-components.md)  
  
-   [パイプライン デザイナーの使用](../core/using-pipeline-designer.md)  
  
-   [パイプライン デザイナーでのパイプラインの作成](../core/creating-pipelines-with-pipeline-designer.md)  
  
-   [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)  
  
-   [パイプラインをデプロイする方法](../core/how-to-deploy-pipelines.md)  
  
-   [パイプラインをセキュリティで保護する方法](../core/how-to-secure-pipelines.md)