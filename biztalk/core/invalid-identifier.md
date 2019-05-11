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
ms.openlocfilehash: 0e277a1b2a02ee622f37007a2d2a001570bded79
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381345"
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
|  メッセージ テキスト   | "{0}"は有効な識別子ではありません。 元の名前を復元します。 (有効な識別子は文字または数字の 0 個以上続く文字から成るし、スペースを含めることはできません)。 |
  
## <a name="explanation"></a>説明  
 このエラーは、スキーマの公開が有効な .net 識別子ではない場合に定義されている web メソッドを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 有効な .net 識別子には、web メソッドを変更します。 有効な識別子では、文字または数字の 0 個以上続く文字で構成され、スペースを含めることはできません。