---
title: "EDI データ要素の構造体要素 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 775e8b87-b952-46d2-a506-5174d216a9aa
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 600edb30ff157a520ac67eebce58428a62e27c8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="edi-data-element-structural-element"></a>EDI データ要素の構造体要素
データ要素は、メッセージのデータの基本単位です。 データ要素は、データ要素区切り記号によって区切られます。データ要素区切り記号は、X12 の場合は既定でアスタリスク、EDIFACT の場合は既定でプラス記号です。 データ要素の選択肢は、必須、オプション、または条件付きとして定義されます。  
  
 データ要素には、単純または複合要素のいずれかを指定できます。 単純データ要素は数値で、最も低いレベルのデータです。 複合データ要素はサブ要素が連結されたもので、サブ要素はコンポーネント区切り記号で区切られた単純データ要素です。 既定では、コンポーネント区切り記号は X12 および EDIFACT のどちらでもコロンです。  
  
 EDIFACT でエンコードされたメッセージの場合、EDI 経由で送信するデータで、区切り記号として使用するように定義された文字を送信する必要があるときは、リリース文字を使用して、後続の文字が区切り記号ではなくデータの一部であることを示す必要があります。 既定では、リリース文字は疑問符 (?) です。  
  
> [!NOTE]
>  X12 ではリリース文字はサポートされていません。 受信側または送信側で、X12 エンコード インターチェンジのデータの一部として区切り記号が見つかった場合、インターチェンジは中断されます。