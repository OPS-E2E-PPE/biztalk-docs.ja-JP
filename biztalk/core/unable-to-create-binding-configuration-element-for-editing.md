---
title: 編集対象のバインド構成要素を作成できません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71853662-5a4a-417e-8160-c93dbcbea336
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98e58ec9966d0e0534d078fc5741f267bf02e735
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974339"
---
# <a name="unable-to-create-binding-configuration-element-for-editing"></a>編集対象のバインド構成要素を作成できません
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                      |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| 製品バージョン |                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                      |
|    イベント ID     |                                                                  0                                                                   |
|  イベント ソース   |                                                                  0                                                                   |
|    コンポーネント    |                                                                  0                                                                   |
|  シンボル名  |                                                                  0                                                                   |
|  メッセージ テキスト   | 編集対象のバインド構成要素を作成できません。 BindingType プロパティおよび BindingConfiguration プロパティの値を確認してください。 |
  
## <a name="explanation"></a>説明  
 ユーザー インターフェイスに表示するバインディング要素を読み込むときに、エラーが発生しました。 このエラーはカスタム バインディングの場合によく発生します。 構成ファイルにバインディング要素がないために、バインディングのドロップダウン リストで使用できない可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 値を確認、 **BindingType**と**BindingConfiguration**プロパティ。  
  
 バインディング構成要素の作成の詳細については、次の情報を参照してください。  
  
-   [WCF-NetMsmq アダプターの構成](../core/configuring-the-wcf-netmsmq-adapter.md)