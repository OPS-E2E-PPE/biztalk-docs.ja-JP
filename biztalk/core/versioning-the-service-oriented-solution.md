---
title: バージョン管理、サービス指向ソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- versioning, service solutions
- service solution tutorial, versioning
ms.assetid: 0e09720f-53f2-4b38-aae3-a79ddfd35be5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34896f02ac6335c8f5041ca959b25fe9ab2716c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393733"
---
# <a name="versioning-the-service-oriented-solution"></a>バージョン管理、サービス指向ソリューション
ソリューションのフロント エンドとして機能する 2 つのオーケストレーション**CustomerServiceReceiveSend**と**CustomerServiceNativeRequestResponse**、中央の動作中のオーケストレーションを呼び出す**CustomerService**します。 オーケストレーションの呼び出しは、オーケストレーションを含むアセンブリのバージョン番号に依存します。 すべての 3 つのオーケストレーションは、同じアセンブリにあるために、バージョン管理の問題はありません。  
  
 さらに、オーケストレーションによって実装されるビジネス プロセスは、すぐに終了する非常に短時間の要求-応答プロセスです。 したがって、バージョン管理、ビジネス プロセスの質問がこのソリューションでは発生しません-さまざまなバージョンでさまざまなアセンブリ内の別のオーケストレーションがありません。  
  
 ただし、オーケストレーションでは、スキーマ アセンブリでスキーマを使用しないでください。 場合は、スキーマが変更され、別のバージョンにコンパイル、スキーマ アセンブリの新しいバージョンでオーケストレーションを再コンパイルする必要があります。  
  
## <a name="see-also"></a>参照  
 [開発、サービス指向ソリューション](../core/developing-a-service-oriented-solution.md)