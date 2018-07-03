---
title: 'シングル サインオン: イベント 10804 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4d98bef-fdc3-4627-bb5b-663fa502b965
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a262448f4d07a01f726f111ca5ddd01901e9e7d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017014"
---
# <a name="single-sign-on-event-10804"></a>シングル サインオン: イベント 10804
## <a name="details"></a>詳細  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10804                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                            なし                             |
|  シンボル名  |                ENTSSO_E_INCORRECT_COMPUTER                 |
|  メッセージ テキスト   |     このアダプターはこのコンピューター用に構成されていません。      |
  
## <a name="explanation"></a>説明  
 各アダプターは特定のコンピューターで実行されるように構成され、コンピューターの長い名前によって識別されます。 この名前が正しくないか、別のコンピューター上のアダプターを実行しようとしています。  
  
## <a name="user-action"></a>ユーザーの操作  
 このアダプターの構成を確認して、適切なコンピューターの正しい名前を特定します。