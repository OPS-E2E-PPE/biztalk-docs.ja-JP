---
title: パイプライン コンポーネントの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, pipeline components [custom]
- pipeline components [custom], deploying
ms.assetid: 98b47fbf-62c0-4012-a406-58c4d56b305a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14ac8f8c91b0ed8b83a6bcbcf4664726c0079515
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389581"
---
# <a name="deploying-pipeline-components"></a>パイプライン コンポーネントの展開
すべての .NET パイプライン コンポーネント アセンブリ (ネイティブおよびカスタム) がである必要があります、 \<*インストール ディレクトリ*\>\Pipeline Components フォルダーに、サーバーによって実行されます。 カスタム コンポーネントを使用して、パイプラインがいくつかのサーバー間でデプロイされる場合、コンポーネントのバイナリがすべてのサーバーで指定したフォルダーに存在する場合があります。  
  
 グローバル アセンブリ キャッシュ (GAC) に BizTalk ランタイムで使用するカスタム パイプライン コンポーネントを追加する必要はありません。  
  
 パイプラインのカスタム COM コンポーネントを COM コンポーネントとしてコンピューターに登録されている限りも、ツールボックスに表示されます。 カスタム .NET パイプライン コンポーネントを配置する必要があります、 \<*インストール ディレクトリ*\>\Pipeline Components フォルダー。  
  
 バイナリ ファイルは、正しい位置には後、は、ツールボックスにコンポーネントを追加する必要があります。 パイプライン コンポーネントをツールボックスに追加する手順については、次を参照してください。[ツールボックスの使用方法](../core/how-to-use-the-toolbox.md)します。  
  
## <a name="see-also"></a>参照  
 [カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)