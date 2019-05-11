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
ms.openlocfilehash: 665b6b00aca8f7f059f021bfc2e1c5803bfc0156
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388764"
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
|  メッセージ テキスト   | このエラーは、ネットワーク共有上にある場合、場所の完全に信頼されたならないことを示します。 ゾーンのコード アクセス セキュリティ ポリシーを確認します。 または、ファイルが BizTalk .NET アセンブリをできない可能性があります。 確認のアセンブリを [アセンブリ。BizTalkAssembly] カスタム属性。 または、ファイルは、.NET アセンブリをできない可能性があります。 ファイルが .dll または .exe の場合は、アンマネージ コードがある可能性があります。 |
  
## <a name="explanation"></a>説明  
 このエラーは、ネットワーク共有上にある場合、場所の完全に信頼されたならないことを示します。 ゾーンのコード アクセス セキュリティ ポリシーを確認します。 または、ファイルが BizTalk .NET アセンブリをできない可能性があります。 確認のアセンブリを [*アセンブリ。BizTalkAssembly*] カスタム属性。 または、ファイルは、.NET アセンブリをできない可能性があります。 ファイルが .dll または .exe の場合は、アンマネージ コードがある可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 信頼できるソースからである場合、場所に許可の完全な信頼レベル。  Dll が有効な BizTalk .net アセンブリであることを確認します。