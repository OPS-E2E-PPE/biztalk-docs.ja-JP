---
title: 'シングル サインオン: イベント 10604 |Microsoft Docs'
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
ms.openlocfilehash: 48996ec333c9035e57393e270db06ca173cfc9e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990587"
---
# <a name="single-sign-on-event-10604"></a>シングル サインオン: イベント 10604
## <a name="details"></a>詳細  
  
|                 |                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------|
|  製品名   |                                        エンタープライズ シングル サインオン                                         |
| 製品バージョン |                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                        |
|    イベント ID     |                                                  10604                                                   |
|  イベント ソース   |                                                  ENTSSO                                                  |
|    コンポーネント    |                                                   なし                                                    |
|  シンボル名  |                                      SSO_ERROR_SSOCSTX_OUT_OF_PROC                                       |
|  メッセージ テキスト   | "ENTSSO Server" COM+ アプリケーションが正しく構成されていません。 COM+ ライブラリ アプリケーションである必要があります。 |
  
## <a name="explanation"></a>説明  
 COM+ アプリケーションは、COM+ ライブラリ アプリケーションとして構成されている必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 ENTSSO MMC スナップインで、COM+ フォルダーを展開し、ENTSSO サーバーを探します。 サーバーを右クリックし、[プロパティ] をクリックします。 [サーバー アプリケーション] ではなく [ライブラリ アプリケーション] を選択し、[OK] をクリックします。