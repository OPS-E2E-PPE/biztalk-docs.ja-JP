---
title: BizTalk Server の以前のバージョンからのスキーマの移行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bdc86401-2002-40b8-a919-2c00cf42b557
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3aabd12fa240688d58cf4c841f0647f2db24df8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396941"
---
# <a name="schema-migration-from-previous-versions-of-biztalk-server"></a>旧バージョンの BizTalk Server からのスキーマの移行
このバージョンの BizTalk Server は XSD (XML Schema Definition) 言語を使用してメッセージ スキーマを表記しますが、旧バージョンは XDR (XML-Data Reduced) 構文を使用してメッセージ スキーマを表記していました。 旧バージョンの BizTalk Server からスキーマを移行する場合、XDR ではなく XSD を使用するようにスキーマを変換する必要があります。  
  
 BizTalk スキーマを XDR 構文から XSD 構文に変換するには、次の作業を実行します。  
  
- スキーマ ファイルの拡張子を .xdr から .xsd に変更します。  
  
- 名前を変更したスキーマを該当する BizTalk プロジェクトに追加します。  
  
- BizTalk エディターで名前を変更したスキーマを開いて、XDR から XSD に変換します。  
  
- スキーマを保存して、変換を永続的にします。  
  
  次の手順を実行する方法の詳細については、次を参照してください。 [XDR スキーマから XSD スキーマを移行する方法](../core/how-to-migrate-xdr-schemas-to-xsd-schemas.md)します。  
  
## <a name="see-also"></a>参照  
 [スキーマについて](../core/about-schemas.md)   
 [XDR スキーマを XSD スキーマに移行する方法](../core/how-to-migrate-xdr-schemas-to-xsd-schemas.md)   
 [フラット ファイル レコードの移行](../core/migrating-flat-file-records.md)