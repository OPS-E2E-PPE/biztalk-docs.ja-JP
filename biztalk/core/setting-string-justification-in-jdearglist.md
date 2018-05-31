---
title: JD Edwards OneWorld アダプターで文字列の位置揃えを設定 |Microsoft ドキュメント
description: BizTalk Server オーケストレーションに、JD Edwards OneWorld アダプターを使用する jdearglist ファイルを更新します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9b013a-839d-45f1-9da0-c96fd45b25e5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70b32d0106d95a1970b480e32dfa47a81ebf98ca
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013001"
---
# <a name="set-string-justification-in-jdearglist"></a>Jdearglist での位置揃えの文字列を設定します。

## <a name="overview"></a>概要
JD Edwards OneWorld の jdearglist.txt ファイルで特定の文字列引数を右揃え (左側に埋め込み) として構成するには、どのビジネス関数にアクセスするのかがわかっている必要があります。特に、ビジネス関数のどのフィールドを呼び出すのかがわかっている必要があります。  
  
 オーケストレーションでバインド (スキーマ) を生成する前に、jdearglist.txt を更新する必要があります。 Jdearglist.txt を更新するための手順が記載されている[文字列値の処理](../core/handling-string-values1.md)です。  
  
 監査ログに jdearglist.txt の警告メッセージが出力された場合は、jdearglist.txt がないことを示しています。 SalesOrder または PurchaseOrder ビジネス関数を実行する場合は、ファイルが PATH に含まれている必要があります。そうでない場合は動作しません。  
  
## <a name="see-also"></a>参照  
[BizTalk Server 例外処理の使用](using-biztalk-server-exception-handling1.md)