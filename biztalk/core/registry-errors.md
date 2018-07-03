---
title: レジストリ エラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a5bf2cd-f807-4083-8687-4416a2ee2908
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62522299866748d92abf91d36a01444c3175b070
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975115"
---
# <a name="registry-errors"></a>レジストリ エラー
診断および WCF のレジストリ エラーを解決するための情報です。  

## <a name="failed-to-access-the-registry"></a>レジストリにアクセスできませんでした
  
|                 |                                   エラーの詳細                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                             HKLM を開けませんでした。\\{0}します。                              |
  
### <a name="explanation"></a>説明  
 このエラーは、レジストリへのアクセスの失敗を示します。  
  
### <a name="user-action"></a>ユーザーの操作  
 レジストリの読み取りアクセス権があることを確認します。 レジストリにアクセスするには、管理者特権があることを確認します。管理者特権がない場合は、コンピューターの管理者に連絡してください。
 
## <a name="failed-to-obtain-biztalk-install-path"></a>BizTalk のインストール パスを取得できませんでした
  
|                 |                                   エラーの詳細                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |             HKLM から BizTalk のインストール パスを取得できませんでした。\\{0}\\{1}              |
  
## <a name="explanation"></a>説明  
 このエラーは、レジストリへのアクセスに失敗し、キーの値が不適切であることを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 レジストリの読み取りアクセス権があることを確認します。 キーの値が正しいことを確認します。 レジストリにアクセスするには、管理者特権があることを確認します。管理者特権がない場合は、コンピューターの管理者に連絡してください。 