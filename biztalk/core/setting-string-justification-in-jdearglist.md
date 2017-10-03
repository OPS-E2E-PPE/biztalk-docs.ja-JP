---
title: "Jdearglist で文字列の位置揃えを設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- jdearglist.txt, setting string justification
- strings, configuring
- strings, right-justified
ms.assetid: 1c9b013a-839d-45f1-9da0-c96fd45b25e5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daecf4101ebf5dc8964562dc7f385d41279a3401
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="setting-string-justification-in-jdearglist"></a>Jdearglist での文字列の位置揃えの設定
JD Edwards OneWorld の jdearglist.txt ファイルで特定の文字列引数を右揃え (左側に埋め込み) として構成するには、どのビジネス関数にアクセスするのかがわかっている必要があります。特に、ビジネス関数のどのフィールドを呼び出すのかがわかっている必要があります。  
  
 オーケストレーションでバインド (スキーマ) を生成する前に、jdearglist.txt を更新する必要があります。 Jdearglist.txt を更新するための手順が記載されている[文字列値の処理](../core/handling-string-values1.md)です。  
  
 監査ログに jdearglist.txt の警告メッセージが出力された場合は、jdearglist.txt がないことを示しています。 SalesOrder または PurchaseOrder ビジネス関数を実行する場合は、ファイルが PATH に含まれている必要があります。そうでない場合は動作しません。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for JD Edwards OneWorld の管理](../core/administering-biztalk-adapter-for-jd-edwards-oneworld.md)