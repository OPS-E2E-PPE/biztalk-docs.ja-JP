---
title: ファイルが BizTalk アセンブリの反映中に例外が発生しましたが見つかりません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 223147eb-785f-4dfc-b2a6-7d50dfaf8092
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804428d71c33d0c45d75443bbc5118a2dfed9ac0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362408"
---
# <a name="a-file-not-found-exception-occurred-while-reflecting-a-biztalk-assembly"></a>BizTalk アセンブリの反映中に、ファイルが見つからないことを示す例外が発生しました
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                                           |
| 製品バージョン |                                                                                                                                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                                                                       |
|    イベント ID     |                                                                                                                                                                   0                                                                                                                                                                    |
|  イベント ソース   |                                                                                                                                                                   0                                                                                                                                                                    |
|    コンポーネント    |                                                                                                                                                                   0                                                                                                                                                                    |
|  シンボル名  |                                                                                                                                                                   0                                                                                                                                                                    |
|  メッセージ テキスト   | ファイルが BizTalk アセンブリの反映中に例外が発生しましたが見つかりません。"{0}"。 この問題は、1 つまたは複数の依存関係が利用できない場合に発生する可能性があります。 この問題を解決するには、次のいずれかを試してください。1. アセンブリの依存関係を同じフォルダーにコピーします。 2. グローバル アセンブリ キャッシュに見つからない依存関係をインストールします。 |

## <a name="explanation"></a>説明  
 このエラーは、公開された参照されている BizTalk アセンブリがないで、グローバル アセンブリ キャッシュ (GAC) または同じディレクトリに別のアセンブリを示します。  

## <a name="user-action"></a>ユーザーの操作  
 エラー メッセージで指定されたアクションだけでなく、参照アセンブリをグローバル アセンブリ キャッシュに移動または BizTalk アセンブリと同じ場所にコピー  

1. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Visual Studio**、順にクリックします**Visual Studio**します。  

2. コマンド プロンプトを開きます。  

3. アセンブリの場所を参照し、入力**gacutil/I/\<**<em>アセンブリ名</em>**\>.dll**
