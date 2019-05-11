---
title: シングル サインオン:イベント 10510 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4553ad4c-9553-4b8b-b3a3-72aed2a61202
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a3ac20c725492ebd6f7867cdf3c11be3ab7fdab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393933"
---
# <a name="single-sign-on-event-10510"></a>シングル サインオン:イベント 10510
## <a name="details"></a>詳細  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10510                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                            該当なし                             |
|  シンボル名  |                  SSO_INFO_DLL_LOAD_FAILED                  |
|  メッセージ テキスト   |   %1 を読み込めませんでした。 このファイルは使用可能なことを確認します。    |

## <a name="explanation"></a>説明  
 この情報イベントは、SSO サービスが、DLL の読み込みに失敗したことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 このイベントを解決するには、次の 1 つ以上の操作を行います。  

- DLL が SSO インストール ディレクトリの通常 C:\Program files \common files \enterprise でシングル サインオンであることを確認します。 SSO インストール ディレクトリは、異なる場合があります。  

- 1 つの DLL が見つからないか壊れている場合、しようとして、サービスを再起動します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [Enterprise Single Sign-On の実装](../core/implementing-enterprise-single-sign-on.md)
