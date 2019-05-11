---
title: シングル サインオン:イベント 10757 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24765a25-560b-4391-9839-a325894c679f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f62cdb2cbf0e5c3ba3477fdfc79376d1c22d3d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307711"
---
# <a name="single-sign-on-event-10757"></a>シングル サインオン:イベント 10757
## <a name="details"></a>詳細  
  
|                 |                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------|
|  製品名   |                                  エンタープライズ シングル サインオン                                   |
| 製品バージョン |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                  |
|    イベント ID     |                                            10757                                             |
|  イベント ソース   |                                            ENTSSO                                            |
|    コンポーネント    |                                             なし                                              |
|  シンボル名  |                                     ENTSSO_E_NO_MAPPING                                      |
|  メッセージ テキスト   | マッピングが存在しません。 構成ストア アプリケーションの場合は、構成情報が設定されていません。 |
  
## <a name="explanation"></a>説明  
 これが単独アプリケーションまたはグループ アプリケーションである場合は、マッピングは存在しません。  
  
 これが構成ストア アプリケーションである場合は、構成データが設定されていません。 このような状況は、SSO データベースが再初期化されているが、BizTalk 管理データベースは再初期化されていない場合、またはその逆の場合に発生します。  
  
## <a name="user-action"></a>ユーザーの操作  
 これが単独アプリケーションまたはグループ アプリケーションである場合は、目的のマッピングを作成します。 詳細については、次を参照してください。[ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md)します。