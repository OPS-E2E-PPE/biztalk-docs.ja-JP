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
ms.openlocfilehash: c508f4839937315c64734f650fe84e87c60c0dcb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292875"
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
|  メッセージ テキスト   | 編集対象のバインド構成要素を作成できません。 BindingType プロパティおよび BindingConfiguration プロパティの値を確認します。 |
  
## <a name="explanation"></a>説明  
 ユーザー インターフェイスに表示するバインド要素を読み込み中にエラーが発生しました。 このエラーは、多くの場合、カスタム バインドで発生します。 バインド要素は、構成ファイルが不足している可能性がありますし、したがってはバインディングのドロップダウン リストで使用できません。  
  
## <a name="user-action"></a>ユーザーの操作  
 値を確認、 **BindingType**と**BindingConfiguration**プロパティ。  
  
 バインディング構成要素を作成する方法の詳細については、次のリソースを参照してください。  
  
-   [WCF-NetMsmq アダプターの構成](../core/configuring-the-wcf-netmsmq-adapter.md)