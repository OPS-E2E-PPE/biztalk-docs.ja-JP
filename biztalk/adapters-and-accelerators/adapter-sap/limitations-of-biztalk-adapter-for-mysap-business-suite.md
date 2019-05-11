---
title: MySAP Business Suite for BizTalk アダプターの制限事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, limitations of
- IDOC, sending an IDOC to an SAP system
ms.assetid: 1ca1e0cf-7ae7-4a8b-8363-e5f3746e8e26
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 828dbca3f4acba3ca76583c21e09bad3e79ba560
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373308"
---
# <a name="limitations-of-biztalk-adapter-for-mysap-business-suite"></a>MySAP Business Suite for BizTalk アダプターの制限事項

## <a name="limitations-list"></a>制限事項の一覧
次の制限事項を呼びます、 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]:  
  
- [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Microsoft BizTalk Adapter for mySAP Business Suite、以前のリリースのアダプターの互換性がありません。 このリリースのアダプターは、アダプターの以前のバージョンを使用して生成されたスキーマのメッセージの送受信をサポートしていません。  
  
- [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ITAB II (階層) テーブルの型を含む、複雑なパラメーター型を持つ Rfc をサポートしていません。  
  
- [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]カスタム ABAP 型を持つ Rfc をサポートしていません。  
  
- 基になるクライアント ライブラリで処理をタイムアウトに関する問題のため、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]コマンドと接続のタイムアウトをサポートしていません。  
  
- BizTalk Server ホストを実行しているコンピューターのシステム時刻を変更する場合、時間は自動的に BizTalk Server ホストで更新されません。 これは、BizTalk Server の受信ポートを使用する受信操作の不適切な動作につながりますでした。 この問題を回避するを実行するコンピューターのシステム時刻を変更した後、受信ポートを持つホスト インスタンスを再起動する必要があります。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for mySAP Business Suite について](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)