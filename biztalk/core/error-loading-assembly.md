---
title: アセンブリの読み込みエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 600973e0-3142-455f-9afa-74430af31e38
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df561b964faa0fae80f41f1423d3034466bbb8ce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994955"
---
# <a name="error-loading-assembly"></a>アセンブリを読み込み中にエラーが発生しました
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                      |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                                                          |
| 製品バージョン |                                                                                                                                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                                                                                      |
|    イベント ID     |                                                                                                                                                                                  0                                                                                                                                                                                   |
|  イベント ソース   |                                                                                                                                                                                  0                                                                                                                                                                                   |
|    コンポーネント    |                                                                                                                                                                                  0                                                                                                                                                                                   |
|  シンボル名  |                                                                                                                                                                                  0                                                                                                                                                                                   |
|  メッセージ テキスト   | このエラーは、読み込み先がネットワーク共有にある場合、完全に信頼されていない可能性があることを示しています。 ゾーンのコード アクセス セキュリティ ポリシーを確認してください。 または、読み込んだファイルが BizTalk .NET アセンブリではない可能性があります。 確認のアセンブリを [アセンブリ: BizTalkAssembly] カスタム属性。 または、読み込んだファイルが .NET アセンブリではない可能性があります。 ファイルが .dll または .exe の場合、これはアンマネージ コードです。 |
  
## <a name="explanation"></a>説明  
 このエラーは、読み込み先がネットワーク共有にある場合、完全に信頼されていない可能性があることを示しています。 ゾーンのコード アクセス セキュリティ ポリシーを確認してください。 または、読み込んだファイルが BizTalk .NET アセンブリではない可能性があります。 確認のアセンブリを [*アセンブリ: BizTalkAssembly*] カスタム属性。 または、読み込んだファイルが .NET アセンブリではない可能性があります。 ファイルが .dll または .exe の場合は、アンマネージ コードがある可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 信頼できる送信元の場合、その送信元に完全信頼を付与します。  dll が有効な BizTalk .NET アセンブリであることを確認します。