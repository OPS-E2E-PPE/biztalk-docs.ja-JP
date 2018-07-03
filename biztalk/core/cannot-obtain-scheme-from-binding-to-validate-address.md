---
title: アドレスの検証にバインドからスキームを取得することはできません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b002084a-63ae-4685-8ce3-88cc6489e19e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2032decfdf59ae175f3ee8fc686341c8a4061fc6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991339"
---
# <a name="cannot-obtain-scheme-from-binding-to-validate-address"></a>アドレスを検証するためのスキームをバインドから取得できません
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |               アドレスを検証するためのスキームをバインドから取得できません。               |
  
## <a name="explanation"></a>説明  
 指定されているトランスポート バインド要素にスキームがありません。  
  
## <a name="user-action"></a>ユーザーの操作  
 トランスポート バインディング要素に有効なスキームがあること、または有効なトランスポート バインディング要素が選択されていることを確認します。 カスタム バインドを使用する場合は、有効なトランスポート バインド要素が指定されていることを確認します。  
  
 詳細については、の次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
-   [WCF-Custom アダプターの構成](../core/configuring-the-wcf-custom-adapter.md)