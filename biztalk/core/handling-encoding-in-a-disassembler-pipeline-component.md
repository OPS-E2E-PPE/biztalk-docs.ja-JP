---
title: 逆アセンブラー パイプライン コンポーネントでのエンコードの処理 |Microsoft Docs
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
ms.openlocfilehash: aaa903b07d0f7661bcf9750b5c8bcd5762e438c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387555"
---
# <a name="handling-encoding-in-a-disassembler-pipeline-component"></a>逆アセンブラー パイプライン コンポーネントでのエンコードの処理
カスタム逆アセンブラー コンポーネントが、次の形式のいずれかで送信ドキュメントをエンコードすることを確認します。  
  
- UTF-8  
  
- UTF-16  
  
- UTF-32  
  
- UTF-16LE  
  
- UTF-16BE  
  
  オーケストレーション エンジンはできない他のエンコード形式でドキュメントを処理することがあります。  
  
  UTF 32LE と UTF 32BE が、.NET Framework でサポートされていませんこれらの形式を使用するには、カスタム エンコード実装を作成する必要があります。  
  
## <a name="see-also"></a>参照  
 [逆アセンブラー パイプライン コンポーネントの開発](../core/developing-a-disassembling-pipeline-component.md)