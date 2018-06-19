---
title: 'シングル サインオン: イベント 10604 |Microsoft ドキュメント'
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
ms.openlocfilehash: 0d9d6858fb13542ca642c9c48a8a187b66ba6526
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270546"
---
# <a name="single-sign-on-event-10604"></a>シングル サインオン: イベント 10604
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10604|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_ERROR_SSOCSTX_OUT_OF_PROC|  
|メッセージ テキスト|"ENTSSO Server" COM+ アプリケーションが正しく構成されていません。 COM+ ライブラリ アプリケーションである必要があります。|  
  
## <a name="explanation"></a>説明  
 COM+ アプリケーションは、COM+ ライブラリ アプリケーションとして構成されている必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 ENTSSO MMC スナップインで、COM+ フォルダーを展開し、ENTSSO サーバーを探します。 サーバーを右クリックし、[プロパティ] をクリックします。 [サーバー アプリケーション] ではなく [ライブラリ アプリケーション] を選択し、[OK] をクリックします。