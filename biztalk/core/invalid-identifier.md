---
title: "識別子が無効です |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f87e1e42-457f-4d04-a1d2-6b796f3fa7b7
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 148b2c2d0b2ec4fb54e15fd8cb50b5dcf0af310a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-identifier"></a>無効な識別子です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|"{0}" は有効な識別子ではありません。 元の名前を復元しています。 (有効な識別子では文字または数字の 0 個以上続く文字から成るし、スペースを含めることはできません)。|  
  
## <a name="explanation"></a>説明  
 このエラーは、スキーマの公開時に定義した Web メソッドが有効な .NET 識別子ではないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 Web メソッドの名前を有効な .NET 識別子に変更します。 有効な識別子の先頭は文字にする必要があり、全体は文字か数字のみで構成されている必要があります。スペースを含めることはできません。