---
title: シングル サインオン:イベント 10512 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edf0512-112d-40b8-9e29-7dd67f999b6d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf29293c12a566a82835510e07f23e52ba0ba243
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243393"
---
# <a name="single-sign-on-event-10512"></a>シングル サインオン:イベント 10512
## <a name="details"></a>詳細  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10512                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                            該当なし                             |
|  シンボル名  |                   SSO_ERROR_LOADLIBRARY                    |
|  メッセージ テキスト   |      %1 を読み込めませんでした %r<br /><br /> エラー コード: %2。       |

## <a name="explanation"></a>説明  
 このエラー イベントは、SSO サーバー プロセスに指定されたダイナミック リンク ライブラリ (DLL) を読み込めなかったことを示します。 セットアップが正常に完了していないこと、またはセットアップ後に、DLL が削除されたことが完了した DLL が SSO インストール ディレクトリの通常 C:\Program files \common files \enterprise でシングル サインオン、不足している可能性があります。 DLL が存在する場合、DLL への正しいパスを解決する SSO サービスに問題があります。 さらに、DLL 自体が破損する可能性があります。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  

- 多くの障害のセットアップが疑われるをアンインストールして、製品を再インストールする必要があります。  

- 1 つの DLL が見つからないか壊れている場合、しようとして、サービスを再起動します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [Enterprise Single Sign-On の実装](../core/implementing-enterprise-single-sign-on.md)
