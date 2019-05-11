---
title: シングル サインオン:イベント 10521 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00d427ff-74d0-45f5-bb55-ab12b564d767
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccb36c1306736fed435099c46254ee34d0079a1d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394352"
---
# <a name="single-sign-on-event-10521"></a>シングル サインオン:イベント 10521
## <a name="details"></a>詳細  

|                 |                                                                       |
|-----------------|-----------------------------------------------------------------------|
|  製品名   |                       エンタープライズ シングル サインオン                       |
| 製品バージョン |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]       |
|    イベント ID     |                                 10521                                 |
|  イベント ソース   |                                ENTSSO                                 |
|    コンポーネント    |                                  該当なし                                  |
|  シンボル名  |                     SSO_ERROR_SECRETS_NOT_LOADED                      |
|  メッセージ テキスト   | マスター シークレット サーバーのレジストリからシークレットを読み込めませんでした。 |

## <a name="explanation"></a>説明  
 マスター シークレットは、レジストリから取得することはできません、マスター シークレット サーバーでこのエラー イベントが発生します。 さらに情報をイベント ログに関連するエラー メッセージが可能性があります。 これの最も可能性の高い原因があったこと、アクセス許可エラーまたは暗号化エラー SSO サービス アカウントは、レジストリにアクセスしようとした場合です。 これは、SSO サービス アカウントが変更されたときに発生します。 マスター シークレットは、SSO サービス アカウントの id に基づくキーで暗号化されます。 そのアカウントが変更された場合、レジストリ内の既存のマスター シークレットは不要になった解読できません。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- マスター シークレットをバックアップするは、SSO サービス アカウントを変更し、マスタ シークレットを復元し、SSO サービス アカウントを変更します。 これは、マスター シークレットを復元でき、このエラーを修正する必要があります。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [マスター シークレット サーバー](../core/master-secret-server.md)  

- [マスター シークレットの管理](../core/managing-the-master-secret.md)  

- [SSO の構成](../core/configuring-sso.md)  

- [SSO のセキュリティに関する推奨事項](../core/sso-security-recommendations.md)
