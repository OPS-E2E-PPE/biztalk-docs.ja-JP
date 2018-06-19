---
title: 逆アセンブラー パイプライン コンポーネントでのエンコードの処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], encoding
- pipeline components [custom], disassembling
ms.assetid: 33420357-421f-4ad0-8eee-d445376676db
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcbfb8f86847668436fae04db7bee1703dfb60ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246706"
---
# <a name="handling-encoding-in-a-disassembler-pipeline-component"></a>逆アセンブラー パイプライン コンポーネントでのエンコードの処理
カスタム逆アセンブラー コンポーネントが次の形式のいずれかで送信ドキュメントをエンコードすることを確認します。  
  
-   UTF-8  
  
-   UTF-16  
  
-   UTF-32  
  
-   UTF-16LE  
  
-   UTF-16BE  
  
 オーケストレーション エンジンでは、他のエンコード形式を使用してドキュメントを処理できない可能性があります。  
  
 UTF-32LE と UTF-32BE は .NET Framework ではサポートされていません。これらの形式を使用するには、カスタム エンコード実装を作成する必要があります。  
  
## <a name="see-also"></a>参照  
 [逆アセンブラー パイプライン コンポーネントの開発](../core/developing-a-disassembling-pipeline-component.md)