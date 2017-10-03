---
title: "BizTalk adapter 用 mySAP Business Suite の制限事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, limitations of
- IDOC, sending an IDOC to an SAP system
ms.assetid: 1ca1e0cf-7ae7-4a8b-8363-e5f3746e8e26
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d392178cd49918151f0ad86c73a5fcba712d6b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="limitations-of-biztalk-adapter-for-mysap-business-suite"></a>BizTalk adapter 用 mySAP Business Suite の制限事項

## <a name="limitations-list"></a>制限事項一覧
次はの既知の制限、 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]:  
  
-   [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Microsoft BizTalk Adapter 用 mySAP Business Suite、以前のリリースのアダプターの互換性がありません。 アダプターのこのリリースは、アダプターの以前のバージョンを使用して生成されたスキーマを持つメッセージの送受信をサポートしていません。  
  
-   [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ITAB II (階層) テーブル型を含む、複雑なパラメーター型での Rfc をサポートしていません。  
  
-   [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]カスタム ABAP 型を持つ Rfc をサポートしていません。  
  
-   基になるクライアント ライブラリによるタイムアウトの処理に関する問題のため、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]コマンドと接続のタイムアウトをサポートしていません。  
  
-   BizTalk Server ホストを実行しているコンピューターのシステム時刻を変更する場合、時間は自動的に BizTalk Server ホストで更新されません。 これは、BizTalk Server の受信ポートを使用する受信操作の不適切な動作をする可能性があります。 この問題を回避するを実行するコンピューターのシステム時刻を変更した後、受信ポートを持つホスト インスタンスを再起動する必要があります。  
  
## <a name="see-also"></a>参照  
 [MySAP Business Suite の BizTalk アダプターを理解します。](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)