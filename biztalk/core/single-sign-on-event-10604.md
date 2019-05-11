---
title: シングル サインオン:イベント 10604 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eea14ab1-5a89-4a62-b414-1bcb36ea339e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 577015af1c021bd17d0d286974e554f9ebf399bc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397766"
---
# <a name="single-sign-on-event-10604"></a>シングル サインオン:イベント 10604
## <a name="details"></a>詳細  
  
|                 |                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------|
|  製品名   |                                        エンタープライズ シングル サインオン                                         |
| 製品バージョン |                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                        |
|    イベント ID     |                                                  10604                                                   |
|  イベント ソース   |                                                  ENTSSO                                                  |
|    コンポーネント    |                                                   なし                                                    |
|  シンボル名  |                                      SSO_ERROR_SSOCSTX_OUT_OF_PROC                                       |
|  メッセージ テキスト   | ' ENTSSO Server' COM + アプリケーションが正しく構成されていません。 COM + ライブラリ アプリケーションでなければなりません。 |
  
## <a name="explanation"></a>説明  
 COM + アプリケーションは、COM + ライブラリ アプリケーションとして構成する必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 ENTSSO MMC スナップインで、COM + フォルダーを展開し、ENTSSO サーバーを検索します。 サーバーを右クリックし、し、[プロパティ] をクリックします。 サーバーのアプリケーションではなくライブラリ アプリケーションを選択し、[ok] をクリックします。