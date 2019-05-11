---
title: パイプラインのテンプレート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, templates
- Pipeline Designer, templates
- send pipelines, templates
- receive pipelines, templates
ms.assetid: b9779159-e49d-47fb-aa1c-06be5d604c67
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c843c4817c8d256f1ac06efbffa741cf88ddc0fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395766"
---
# <a name="pipeline-templates"></a>パイプライン テンプレート
既定のパイプラインだけでなく[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2 つのパイプライン テンプレートが含まれています: 受信パイプライン テンプレートと送信パイプライン テンプレート。 Microsoft での BizTalk プロジェクトから[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、パイプライン テンプレートをプロジェクトに追加するにを使用して、**新しい項目の追加**コマンドを**プロジェクト**メニュー。 各テンプレートにはポリシー ファイルが関連付けられ、このポリシー ファイルによって、パイプラインに含まれるステージと、パイプラインで許可されるパイプライン コンポーネントが決まります。 ポリシー ファイルにおけるステージの順序を変えることはできませんが、パイプライン デザイナーを使って、ステージにおけるコンポーネントの順序を変えることはできます。  
  
 ポリシー ファイルでは、次の情報が指定されます。  
  
- ステージの順序  
  
- ステージあたりの最大コンポーネント数  
  
- 各ステージの実行モード  
  
  パイプライン テンプレートのポリシー ファイルに格納されます *\<BizTalk Server のインストール ディレクトリ\>* \Developer Tools\Pipeline ポリシー ファイルです。 ポリシー ファイルは編集しないでください。 パイプラインに変更を加える場合は、パイプライン テンプレートを開き、パイプライン デザイナーを使って編集します。 パイプライン デザイナーの使用に関する詳細については、次を参照してください。[パイプライン デザイナーを使用して](../core/using-pipeline-designer.md)します。  
  
  空のパイプライン テンプレート ファイルが格納されている *\<BizTalk Server のインストール ディレクトリ\>* \Developer Tools\BizTalkProjectItems、されが BTSReceivePipeline.btp および BTSTransmitPipeline.btp という名前. ファイル名の拡張子 .btp は、ファイルが BizTalk Server パイプラインは、パイプライン デザイナーで編集できることを示します。  
  
## <a name="see-also"></a>参照  
 [パイプラインの種類](../core/types-of-pipelines.md)   
 [パイプライン コンポーネントの種類](../core/types-of-pipeline-components.md)   
 [既定のパイプライン](../core/default-pipelines.md)   
 [パイプライン コンポーネント](../core/pipeline-components.md)   
 [パイプライン、ステージ、およびコンポーネントについて](../core/about-pipelines-stages-and-components.md)