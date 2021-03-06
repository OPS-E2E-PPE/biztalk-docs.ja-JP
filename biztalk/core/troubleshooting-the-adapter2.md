---
title: トラブルシューティング、Adapter2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- wildcard characters, in send port properties
- troubleshooting adapter
- Get.xml
- send ports, using wildcards in properties
ms.assetid: e9e0408f-5a12-4f05-83a6-37dc519ae4c5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 556cf4eea03af072e5b42a5748482c4e60a5a5d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306400"
---
# <a name="troubleshooting-the-adapter"></a>アダプターのトラブルシューティング
このトピックでは、Microsoft BizTalk Adapter for PeopleSoft Enterprise の使用中に発生する可能性がある問題の特定と解決に役立つ情報を提供します。  
  
## <a name="cannot-use-wildcard-characters-in-send-port-properties"></a>送信ポートのプロパティにワイルドカード文字を使用できない  
 BizTalk Adapter for PeopleSoft Enterprise では、以下の送信ポート プロパティ フィールドにワイルドカード文字を使用できません。  
  
-   [ユーザー名]  
  
-   App Server Path  
  
-   Java_Home  
  
-   People JAR Files  
  
## <a name="getxml-data-assigns-0001-01-01-value-for-null-dates"></a>Get.xml データにより Null の日付に 0001-01-01 値が割り当てられる  
 Get.xml データは、Null の日付に無効な 0001-01-01 値を割り当てます。 0001-01-01 を Null に修正する場合は、BizTalk マッパー ツールを使用する必要があります。  
  
## <a name="creating-and-updating-properties-with-collections-fails"></a>コレクションでのプロパティの作成および更新に失敗する  
 このアダプターと PeopleSoft version 8.17.02 を併用すると、アダプターは PeopleSoft サーバーからデータを正しく読み取ります。 ただし、コレクションでのプロパティの作成および更新には失敗します。 これは、PeopleSoft の既知の問題で、今後の PeopleSoft リリースで修正される可能性があります。  
  
## <a name="see-also"></a>参照  
 [PeopleSoft のトラブルシューティング](../core/troubleshooting-peoplesoft.md)