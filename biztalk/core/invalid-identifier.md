---
title: 識別子が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f87e1e42-457f-4d04-a1d2-6b796f3fa7b7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41b349991d0e0d6949754c804fcd1ebf16ea7ad1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012355"
---
# <a name="invalid-identifier"></a>無効な識別子です
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                             |
| 製品バージョン |                                                        [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                         |
|    イベント ID     |                                                                                     0                                                                                     |
|  イベント ソース   |                                                                                     0                                                                                     |
|    コンポーネント    |                                                                                     0                                                                                     |
|  シンボル名  |                                                                                     0                                                                                     |
|  メッセージ テキスト   | "{0}"は有効な識別子ではありません。 元の名前を復元しています。 (有効な識別子は文字または数字の 0 個以上続く文字から成るし、スペースを含めることはできません)。 |
  
## <a name="explanation"></a>説明  
 このエラーは、スキーマの公開時に定義した Web メソッドが有効な .NET 識別子ではないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 Web メソッドの名前を有効な .NET 識別子に変更します。 有効な識別子の先頭は文字にする必要があり、全体は文字か数字のみで構成されている必要があります。スペースを含めることはできません。