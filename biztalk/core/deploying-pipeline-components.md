---
title: "パイプライン コンポーネントの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, pipeline components [custom]
- pipeline components [custom], deploying
ms.assetid: 98b47fbf-62c0-4012-a406-58c4d56b305a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84ee3255c38e26c5f5d6d19797cba03ba549668b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-pipeline-components"></a>パイプライン コンポーネントの展開
すべての .NET パイプライン コンポーネント アセンブリ (ネイティブおよびカスタム) がである必要があります、 \<*インストール ディレクトリ*> \Pipeline Components フォルダー、サーバーによって実行されます。 カスタム コンポーネントを持つパイプラインを複数のサーバーに展開するには、各サーバー上の指定のフォルダーに、コンポーネントのバイナリが存在する必要があります。  
  
 BizTalk ランタイムで使用するカスタム パイプライン コンポーネントを、グローバル アセンブリ キャッシュ (GAC) に追加する必要はありません。  
  
 パイプラインのカスタム COM コンポーネントも、そのコンピューターに COM コンポーネントとして登録されている限り、ツールボックスに表示されます。 カスタム .NET パイプライン コンポーネントを配置する必要があります、 \<*インストール ディレクトリ*> \Pipeline Components フォルダーです。  
  
 バイナリ ファイルを正しい場所に配置した後、コンポーネントをツールボックスに追加する必要があります。 パイプライン コンポーネントをツールボックスに追加する方法の詳細については、次を参照してください。[ツールボックスの使用方法](../core/how-to-use-the-toolbox.md)です。  
  
## <a name="see-also"></a>参照  
 [カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)