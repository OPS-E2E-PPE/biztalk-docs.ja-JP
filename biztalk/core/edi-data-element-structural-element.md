---
title: EDI データ要素の構造体要素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 775e8b87-b952-46d2-a506-5174d216a9aa
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b36433f3cf4cf4a8f14ac70467d870a727db7dd9
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530830"
---
# <a name="edi-data-element-structural-element"></a>EDI データ要素の構造体要素
データ要素は、メッセージ内のデータの主要な単位です。 データ要素は、既定では X12 の場合は、アスタリスク、EDIFACT の場合、既定でプラス記号であるデータ要素区切り記号で区切られます。 データ要素の選択肢は、必須、オプション、または条件付きとして定義されます。  
  
 データ要素には、単純または複合のいずれかを指定できます。 単純データ要素は数値でデータの最下位レベル。 複合データ要素は、コンポーネントの区切り記号で区切られた単純データ要素には、サブ要素の連結です。 既定では、コンポーネントの区切り記号は X12 と EDIFACT のコロンです。  
  
 EDIFACT でエンコードされたメッセージでは、EDI 経由で送信されるデータは、区切り記号として使用するために定義された文字を送信する必要がある場合たいリリース文字を使用して、次の文字が区切り記号でないが、データの一部であることを示します。 リリース文字は、疑問符 (?) で、既定です。  
  
> [!NOTE]
>  X12 では、リリース文字はサポートされていません。 区切り記号が、受信または送信のいずれかの側で、X12 エンコード インターチェンジのデータの一部として発生した場合、インターチェンジは中断されます。