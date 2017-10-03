---
title: "無効または見つからない ASN.1 圧縮データ OID 圧縮解除処理中に発生した |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0171daa8-289a-43f1-8cbf-d779ef9dc2ea
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05af1fc0c9f6516f180cf629cd0a21d838f0b4f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-or-missing-asn1-compressed-data-oid-encountered-during-decompression-processing"></a>圧縮解除処理中に無効な ASN.1 圧縮データ OID が検出されたか、ASN.1 圧縮データ OID が見つかりませんでした
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|-|  
|メッセージ テキスト|圧縮解除処理中に無効な ASN.1 圧縮データ OID が検出されたか、ASN.1 圧縮データ OID が見つかりませんでした|  
  
## <a name="explanation"></a>説明  
 このエラーは、圧縮データの ASN.1 構造に関係しています。 このエラーは、圧縮データの送信者が作成した圧縮データの構造に誤りがあるか、メッセージの改ざん (無許可の変更) があったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 圧縮データの構造を見直し、メッセージの改ざんがないかどうかを確認します。